<%*
/**
 * Script to inject page count using HTML comments (invisible on Publish)
 */
const dv = app.plugins.plugins["dataview"].api;
const openPublishPanel = app.commands.commands["publish:view-changes"].callback;

// 1. Configuration
// Change "Home" to the exact name of your homepage file (e.g., "index" or "Dashboard")
const homePagePath = "Home"; 
const totalPages = dv.pages('!"Templates"').length;

// 2. Find the Homepage file
const homeFile = tp.file.find_tfile(homePagePath);

if (homeFile) {
    let content = await app.vault.read(homeFile);

    // 3. Regex to find HTML comments
    // This looks for: <!-- COUNT_START --> any_text <!-- COUNT_END -->
    const regex = /<!-- COUNT_START -->.*?<!-- COUNT_END -->/g;
    const newSnippet = `<!-- COUNT_START -->${totalPages.toLocaleString()}<!-- COUNT_END -->`;
    
    if (regex.test(content)) {
        const updatedContent = content.replace(regex, newSnippet);
        
        // 4. Update the file if changed
        if (content !== updatedContent) {
            await app.vault.modify(homeFile, updatedContent);
            new Notice(`Updated Homepage to ${totalPages} pages.`);
        } else {
            new Notice("Page count is already up to date.");
        }
    } else {
        new Notice("⚠️ Error: Couldn't find the <!-- COUNT_START --> markers!");
    }
} else {
    new Notice(`⚠️ Error: Could not find file: ${homePagePath}`);
}

// 5. Open the Publish panel
openPublishPanel();
%>