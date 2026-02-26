```js
(async () => {
    const fs = require('fs');
    const path = require('path');
    const { exec: execCB, spawnSync } = require('child_process');
    const util = require('util');
    const exec = util.promisify(execCB);

    // --- CONFIGURATION ---
    const ANACONDA_ACTIVATE = "C:/Users/htmlp/anaconda3/Scripts/activate.bat";
    const CONDA_HOME = "C:/Users/htmlp/anaconda3";
    
    // File Paths
    const workDir = path.resolve('./temp_jobs');
    const originalImage = path.join(workDir, 'test.png');
    
    // Intermediate naming conventions
    const img_cliopatria = path.join(workDir, 'test_cliopatria.png');
    const img_expanded = path.join(workDir, 'test_cliopatria_expanded.png');
    const img_equirectangular = path.join(workDir, 'test_equirectangular.png');
    
    // Ensure working directory exists
    if (!fs.existsSync(workDir)) fs.mkdirSync(workDir, { recursive: true });

    try {
        console.log("Starting Processing Chain...");

        // ---------------------------------------------------------
        // PRE-STEP: Malformed Robinson -> Cliopatria Robinson
        // ---------------------------------------------------------
        console.log(`[1/5] Normalising Malformed Robinson to Cliopatria...`);
        // Your provided specific command:
        await exec(`magick "${originalImage}" -resize 4728x2647! -background black -extent 4800x2400-93+82 "${img_cliopatria}"`);


        // ---------------------------------------------------------
        // STEP A: Normalise Robinson (A_normaliseRobinson)
        // Logic: -background none -splice 160x0
        // ---------------------------------------------------------
        console.log(`[2/5] Expanding Robinson (Method A)...`);
        await exec(`magick "${img_cliopatria}" -background none -splice 160x0 "${img_expanded}"`);


        // ---------------------------------------------------------
        // STEP B: Convert to Equirectangular (B_convertRobinsonToEquirectangular)
        // Logic: Anaconda Activate -> GDAL Chain
        // ---------------------------------------------------------
        console.log(`[3/5] Converting to Equirectangular (Method B)...`);
        
        // Define temporary TIFF paths
        const t1 = path.join(workDir, 'temp_t1.tif');
        const t2 = path.join(workDir, 'temp_t2.tif');

        // Construct the GDAL Chain string exactly as provided in the class
        // Note: Using the specific extent and resolution from B_convertRobinsonToEquirectangular
        const gdal_chain = [
            `gdal_translate -a_srs "ESRI:54030" -a_ullr -17035872.77 8542325 17035872.77 -7944003 "${img_expanded}" "${t1}"`,
            `gdalwarp -t_srs "EPSG:4326" -te -180 -90 180 90 -tr 0.083333333333333 0.083333333333333 -r near -wo SOURCE_EXTRA=1000 -wo SAMPLE_STEPS=1000 "${t1}" "${t2}"`,
            `gdal_translate -of PNG "${t2}" "${img_equirectangular}"`,
            `del "${t1}" "${t2}"` // Cleanup TIFFs immediately as per original code logic
        ].join(' && ');

        // Create the Batch file to handle Anaconda environment activation
        const batContent = [
            `@echo off`,
            `cmd /C "call "${ANACONDA_ACTIVATE}" "${CONDA_HOME}" && ${gdal_chain}"`
        ].join('\r\n');

        const batFilePath = path.join(workDir, `job_conversion.bat`);
        fs.writeFileSync(batFilePath, batContent, 'utf8');

        // Execute Batch file synchronously (mimicking the mutex lock in the original code)
        const result = spawnSync('cmd.exe', ['/c', `"${batFilePath}"`], {
            shell: true,
            stdio: 'inherit',
        });

        if (result.status !== 0) {
            throw new Error(`GDAL conversion failed with status ${result.status}`);
        }

        // Clean up the batch file
        if (fs.existsSync(batFilePath)) fs.unlinkSync(batFilePath);
        
        // Small delay as requested in original code (Anaconda resolve wait)
        await new Promise((resolve) => setTimeout(resolve, 1500));


        // ---------------------------------------------------------
        // STEP C: Delete Aux XML Files (C_deleteAuxXMLFiles)
        // ---------------------------------------------------------
        console.log(`[4/5] Cleaning up XML artifacts (Method C)...`);
        const auxFile = `${img_equirectangular}.aux.xml`;
        if (fs.existsSync(auxFile)) {
            fs.unlinkSync(auxFile);
        }


        // ---------------------------------------------------------
        // STEP D: Normalise Equirectangular (D_normaliseEquirectangular)
        // Logic: -roll +126+0
        // ---------------------------------------------------------
        console.log(`[5/5] Normalising Equirectangular Roll (Method D)...`);
        if (fs.existsSync(img_equirectangular)) {
            await exec(`magick "${img_equirectangular}" -roll +126+0 "${img_equirectangular}"`);
            console.log(`\nSUCCESS: Image saved to ${img_equirectangular}`);
        } else {
            console.error("Error: Expected output file missing after GDAL step.");
        }

    } catch (e) {
        console.error("CRITICAL ERROR:", e);
    }
})();
```