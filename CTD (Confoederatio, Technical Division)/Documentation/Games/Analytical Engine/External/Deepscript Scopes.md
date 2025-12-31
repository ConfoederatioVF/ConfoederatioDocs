**Logic (Scopes).**

**Scopes** refer to the local context in which a series of effects or conditions are calculated. By default, these come in two different types: **Internal Scopes** which are used internally by **Analytical Engine**’s logic when parsing DeepScript files, and **External Scopes** which are used to change the gamestate directly.

**Custom UI Scope.**

- addCustomUI(arg0\_options)  
  - id: (String) \- The ID of the Custom UI to use in main.interfaces.  
  - pages: (Array\<String\>) \- The pages on which to display the menu.  
      
  - options: (Object)  
    - id: (String)  
    - name: (String)  
    - no\_title: (Boolean)  
        
    - anchor: (String)  
    - can\_close: (Boolean)  
    - do\_not\_display: (Boolean) \- Whether to display the menu or simply return its form without .menu\_obj;  
    - draggable: (Boolean)  
    - has\_back\_button: (Boolean)  
    - lock\_hover: (Boolean)  
    - pinned: (Boolean)  
    - persistent: (Array\<String\>)  
    - raw\_coords: (Boolean)  
    - resizeable: (Boolean)  
        
    - height: (Number)  
    - width: (Number)  
    - x: (Number)  
    - y: (Number)  
        
    - \<ui\_element\_key\>: (Object)  
      - name: (String)  
      - type: (String) \- Either 'bar\_chart'/'button'/'flag\_button'/'large\_flag\_button'/'line\_graph'/'minimap'/'pie\_chart'/'pie\_chart\_with\_stats'/'scroll\_text'/'slider'/'text'.  
      - raw\_coords: (Boolean) \- Whether to use raw specified coords instead of autoformatting.  
      - raw\_dimensions: (Boolean) \- Whether to override default multiplication for .width.  
          
      - height: (Number) \- Optional. The height as multiplied by CFG.BUTTON\_WIDTH. 2 by default.  
      - width: (Number) \- Optional. The width as multiplied by CFG.BUTTON\_WIDTH. 2 by default.  
      - x: (Number) \- Optional. Auto-formatted by default.  
      - y: (Number) \- Optional. Auto-formatted by default.  
          
      - align: (String) \- Optional. Either 'left', 'centre', or 'right'.  
      - clickable: (Boolean) \- Optional. Whether the element is clickable. True by default.  
      - special\_function: (Function) \- The function to fire upon element click. Feeds (e) as parameters.  
        - (e): (Object)  
          - element: (Object, MenuElement)  
          - interface\_obj: (Object, Interface)  
            - logic\_loop: (Function)  
            - menu\_obj: (Object, Menu)  
      - tooltip: (LocalisationString)  
  - init\_function: (Function) \- Feeds (arg0\_interface\_obj) as parameters.  
  - pre\_init\_function: (Function) \- Feeds (arg0\_interface\_obj) as parameters.  
  - update\_function: (Function) \- Feeds (arg0\_interface\_obj) as parameters.  
  - update\_interval: (Number) \- Optional. How often to run the update function. 100 by default.  
- openKeyboardPrompt(arg0\_variable\_key, arg1\_options)  
  - arg0\_variable\_key: (String) \- The variable name to save the keyboard prompt to.  
  - arg1\_options: (Object)  
    - placeholder: (String)  
    - special\_function: (Function) \- The function to fire upon keyboard close. Feeds (e) as parameters.  
      - (e): (String) \- The string that fires upon keyboard close.

**Event Scope.**

- addEvent(arg0\_options)  
  - id: (String) \- The ID of the event.  
  - image: (String) \- The filepath to the event image to display.  
  - type: (String) \- Either ‘civ\_event’/’mission\_event’/’province\_event’.  
      
  - name: (String) \- The name of the event.  
  - description: (String)

- display\_in\_missions: (Boolean)  
- mission\_id: (Number) \- If defined, this will display in missions unless told not to explicitly.  
- only\_once: (Boolean)

- effect: (Function)  
- immediate: (Function)  
- limit/trigger: (Function)


  - btn\_\<key\>: (Object)  
    - name: (String)  
    - description: (LocalisationString)  
        
    - ai\_chance: (Number/Value)  
    - disabled: (Boolean)  
    - effect: (Function)  
    - limit: (Function)

    

**Gamestate Scopes (External).**

- onGameStart(arg0\_function)  
    
- allCivilisationsScope(arg0\_function)  
  - (arg0\_civ\_obj)  
- allProvincesScope(arg0\_function)  
  - (arg0\_province\_obj)  
- anyCivilisationScope(arg0\_limit\_function, arg1\_function)  
  - (arg0\_civ\_obj)  
- anyProvinceScope(arg0\_limit\_function, arg1\_function)  
  - (arg0\_province\_obj)  
- civilisationScope(arg0\_civ\_tags, arg1\_function)  
  - (arg0\_civ\_obj)  
- globalScope(arg0\_function)  
- internationalOrganisationScope(arg0\_international\_organisation\_tags, arg1\_function) **\[WIP\]**  
  - (arg0\_international\_organisation\_obj)  
- provinceScope(arg0\_provinces, arg1\_function)  
  - (arg0\_province\_obj)


  **Sub-Province Gamestate Scopes. \[WIP\]**

- allBuildingsScope(arg0\_provinces, arg1\_function)  
  - (arg0\_building\_obj)  
- allPopsScope(arg0\_provinces, arg1\_function)  
  - (arg0\_pop\_obj)  
- allWealthPoolsScope(arg0\_provinces, arg1\_function)  
  - (arg0\_wealth\_pool\_obj)  
- anyBuildingsScope(arg0\_provinces, arg1\_limit\_function, arg2\_function)  
  - (arg0\_building\_obj)  
- anyPopsScope(arg0\_provinces, arg1\_function)  
  - (arg0\_pop\_obj)  
- anyWealthPoolsScope(arg0\_provinces, arg1\_function)  
  - (arg0\_wealth\_pool\_obj)

**Mapmode Scope.**

- addMapmode(arg0\_options) \- Adds a modded in-game mapmode to config.mapmodes.  
  - id: (String) \- The ID of the mapmode to declare in config.mapmodes. Best practices indicate that you should have a dedicated mod ID as a namespace.  
  - name: (String) \- The in-game display name for your mapmode.  
      
  - is\_editor\_mapmode: (Boolean) \- Optional. Whether this is an editor mapmode. False by default.  
  - is\_game\_mapmode: (Boolean) \- Optional. Whether this is an in-game mapmode. False by default.  
  - live\_update: (Boolean) \- Optional. Whether this mapmode should update live. Decreases performance at the cost of a live update loop. False by default.  
  - separate\_mapmode: (Boolean) \- Optional. Whether this is a fully-fledged mapmode, or a sub-mapmode of the pre-existing applied mapmode.  
  - special\_function: (Function) \- Must return an RGBA value for all provinces in array format, \[0-255, 0-255, 0-255, 0-1\]. Passes (province\_obj). Undefined assumes a fully transparent province.

**On Action Scopes.**  
On Action Scopes trigger upon a given gamestate change or interaction (e.g. loading a new scenario, changing tags, clicking on a province, game ticks, etc). They can be used to load in functions and effects to evaluate custom mechanics.

**Game Interactions.**  
**Game.**

- onArmyDisband(arg0\_function)  
  - (arg0\_options)  
    - army\_obj: (Object)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
- onArmyRecruitment(arg0\_function)  
  - (arg0\_options)  
    - army\_obj: (Object)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_obj: (Object)  
    - province\_id: (String)  
- onBuildingConstruction(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)

      

    - building\_key: (String)  
    - building\_obj: (Object)  
- onRival(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - ot\_civ\_obj: (Object)  
    - ot\_civ\_tag: (String)  
- onSiegeEnd(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - ot\_civ\_obj: (Object)  
    - ot\_civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onWar(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - ot\_civ\_obj: (Object)  
    - ot\_civ\_tag: (String)  
    - war\_obj: (Object)

    

- onWarEnd(arg0\_function)  
  - (arg0\_options)  
    - attackers: (Array\<String, CivTag\>)  
    - defenders: (Array\<String, CivTag\>)  
    - war\_obj: (Object)

      

    **Map.**

- onCivilisationClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)

      

    - player\_obj: (Object)  
    - player\_tag: (String)  
- onProvinceClick(arg0\_function)  
  - (arg0\_options)  
    - province\_id: (String)  
    - province\_obj: (Object)

    

    **Province.**

- onProvinceRename(arg0\_function)  
  - (arg0\_options)  
    - province\_id: (String)  
    - province\_obj: (Object)

      

    - old\_province\_name: (String)  
    - new\_province\_name: (String)

      

- onProvinceBuildClick(arg0\_function)  
  - (arg0\_options)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceBuildingClick(arg0\_function)  
  - (arg0\_options)  
    - province\_id: (String)  
    - province\_obj: (Object)  
    - building\_obj: (Object)  
    - building\_key: (String)  
- onProvinceBonusModifiersClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceCoresClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceDefenceLevelClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceDevastationClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceEconomyClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceInfrastructureClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceLootClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceManpowerClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceMonthlyIncomeClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvincePopulationChartClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceReligionClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceResourceClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceTaxEfficiencyClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceTerrainPictureClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceUnrestClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)  
- onProvinceValueClick(arg0\_function)  
  - (arg0\_options)  
    - civ\_obj: (Object)  
    - civ\_tag: (String)  
    - province\_id: (String)  
    - province\_obj: (Object)

    

  **Gamestate Loops.**

- onGameTick(arg0\_function)  
    
- onGameDailyInterval(arg0\_function)  
- onGameMonthlyInterval(arg0\_function)  
- onGameYearlyInterval(arg0\_function)  
    
  **Menu Interactions.**  
- onEditorClick(arg0\_function)  
- onGameExit(arg0\_function)  
- onNewScenario(arg0\_function)


- onGameLoad(arg0\_function)  
  - (arg0\_loadgame\_path)  
- onGameSave(arg0\_function)  
  - (arg0\_savegame\_path)  
- onGameStartup(arg0\_function)
