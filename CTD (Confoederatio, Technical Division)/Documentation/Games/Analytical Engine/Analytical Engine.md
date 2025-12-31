#wip 

> [!WARNING]
> This page is currently **malformed**. Consider editing this page to improve its formatting.

# Documentation

**External:**
- [[Mod File Structure]]
  
- [[Deepscript Conditionals]]
- [[Deepscript Effects]]
- [[Deepscript Scopes]]
- [[Deepscript Variables]]
  
- [[Deepscript Backlog]]

**Internal:**
- [[(Global, Internal) config]]
- [[(Global, Internal) Custom UIs]]
- [[(Internal) Map Data Scripting]]
# README
[View on GitHub](https://github.com/Confoederatio/AnalyticalEngine)

[![AnalyticalEngine - Icon](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.eddb728a58f047bdff0a795dfcf7a008.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.e21bc626b8d2254c269f9b99ce170e53.png "Unavailable")

**AOC3, Open Sourced.**

Take a sledgehammer to those modding restrictions.

---

[![Join our community!](https://camo.githubusercontent.com/c6988d57aea47d3fd68a32a6402d3082745934a2fc67618e2f7406bc2663052b/68747470733a2f2f696d672e736869656c64732e696f2f646973636f72642f3534383939343734333932353939373537303f6c6162656c3d446973636f7264267374796c653d666f722d7468652d6261646765)](https://discord.gg/89kQY2KFQz) [![68747470733a2f2f696d672e736869656c64732e](https://camo.githubusercontent.com/aa797b9f75f010662f9681ec901cd8e9d0778bd12247021bf48858a215b298f2/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c616e6775616765732f636f64652d73697a652f4175737472616c69732d302f416e616c79746963616c456e67696e653f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/aa797b9f75f010662f9681ec901cd8e9d0778bd12247021bf48858a215b298f2/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c616e6775616765732f636f64652d73697a652f4175737472616c69732d302f416e616c79746963616c456e67696e653f7374796c653d666f722d7468652d6261646765)

**AnalyticalEngine** (Project Orion) is a game engine that opens up the core binary code of AOC3 and removes hardcoded features and mechanics by allowing for full NashornJS scripting in mods, as well as providing an API for Event Conditions, Effects, Game Scopes, modded Multiplayer (MP) support, and custom mapmodes and UIs. This allows for full hybrid Java and JavaScript modding support.

To get started with modding in AnalyticalEngine, simply add .ds/.js files in your mod folder. These will be automatically detected by the game engine and executed in-game. Consider also reading the attached **Documentation** or asking for support from our Discord server.

**Installation:** [GitHub](https://github.com/Confoederatio/AnalyticalEngine/) | [Steam](https://steamcommunity.com/sharedfiles/filedetails/?id=3429582135)

**Latest Release:** [0.6b - Centurion](https://github.com/Confoederatio/AnalyticalEngine/releases/tag/beta-0.6.0-centurion). (Make sure to check GitHub installation instructions before downloading).

1. Install [Java SDK 23](https://www.oracle.com/uk/java/technologies/downloads/).
2. Download the current src/AOC3-Source.jar, and drop it into any basegame AOC3 directory.
3. You may now either run it normally as a Java binary or via the command line in the extracted folder if you wish to access AnalyticalEngine's console: `java -jar src/AOC3-Source.jar`

`-`

[![image.thumb.png.2dc0a90ae42b6511db3d57f9c88b02b0.png](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.2dc0a90ae42b6511db3d57f9c88b02b0.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.30cdb7779c9ea13d4d8b6ba88e07486a.png "Unavailable")

**Documentation:**

**Note:** Documentation is currently a work-in-progress and may not necessarily be complete.

- [Custom Mapmodes](https://docs.google.com/document/d/1BiNkR2viT5-brjBGan3dNHYvwu2Qn-TWQEktjVsJ-44/edit?usp=sharing)
- [Deepscript (Event Conditions, Effects, Loops, Scopes, Variables)](https://docs.google.com/document/d/1cgZIJyXivPmHRlPZBEmlv65Aypafa_xPVOjqJDaS6Sg/edit?usp=sharing)
- [Map Data Scripting Information](https://docs.google.com/document/d/1zXPs4nmJdrDUInwI-_gfCVnCAFQaagksDPb1qgpR9uA/edit?usp=sharing)
- [Nashorn Scripting](https://docs.oracle.com/javase/8/docs/technotes/guides/scripting/nashorn/)

**Features:**

[![image.thumb.png.64ad4b0f03eff7f44db0d3d9c4db0be5.png](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.64ad4b0f03eff7f44db0d3d9c4db0be5.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.33fbc718377f54eaf5a91cb8b9b13aaa.png "Unavailable")

**Current Feature List.**

- Added Singleplayer support for the Multiplayer build of the game.
- Custom Event support.
- Custom Mapmode support.
- Custom UI support.
- Fixed various localisation glitches.
- Fixed various map glitches.
- Full NashornJS compatibility and scripting.
- Modded Multiplayer support.
- Overhauled Editor UIs:
    - Civilisations can now be directly edited by right clicking on a Civilisation in the Scenario Editor.
    - Province Names can be edited directly from in-game editors.
    - Resource Editor overhaul.
    - Scenario Editor overhaul.
    - Terrain Editor overhaul.
- Overhauled tooltips now allow for inline coloured text changes and images in Events.
- Reworked Conditions (Triggers) and Scopes.

-

[![image.thumb.png.4e3362206d843fec30972ad385199e65.png](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.4e3362206d843fec30972ad385199e65.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.1672bd07aabd7238f5aa01eb2030bb9b.png "Unavailable")[![image.thumb.png.b23e876e376c4fffcde7c4d01e8e8e75.png](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.b23e876e376c4fffcde7c4d01e8e8e75.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.6aa42e01cf9a70018b492623bc6bfbe0.png "Unavailable")

[![image.thumb.png.011741256590e6844d9cda105bddad7f.png](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.011741256590e6844d9cda105bddad7f.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.513bdb1fbeab133ba399322e05a266a0.png "Unavailable")[![image.thumb.png.a3a2367d9f15b7a1a738d140ba42b255.png](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.a3a2367d9f15b7a1a738d140ba42b255.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.bad7cbdef35ced877e67e994cedb998b.png "Unavailable")

[![image.png](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.thumb.png.814edc21202e2e2be6d3a60065d23880.png "Unavailable")](http://www.ageofcivilizationsgame.com/uploads/monthly_2025_02/image.png.21ac79627ee3df7ca2d4dfba39f89a52.png "Unavailable")