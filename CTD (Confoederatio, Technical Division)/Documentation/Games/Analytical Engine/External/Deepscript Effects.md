**Logic (Effects).**

**Abstract.**

**Effects** take place in designated **Effect Functions** or in custom functions designed by the user. They may contain custom embedded JS logic and can manipulate game internals.

**Meta Effects. \[WIP\] \- Add multiple functions for making iterative loops easier.**

Variables.  
getCivilisationFlag(arg0\_civ\_tag, arg1\_flag\_key)  
getGlobalFlag(arg0\_flag\_key)  
getProvinceFlag(arg0\_province, arg1\_flag\_key)  
setCivilisationFlag(arg0\_civ\_tag, arg1\_flag\_key)  
setGlobalFlag(arg0\_flag\_key)  
setProvinceFlag(arg0\_province, arg1\_flag\_key)  
removeCivilisationFlag(arg0\_civ\_tag, arg1\_flag\_key)  
removeGlobalFlag(arg0\_flag\_key)  
removeProvinceFlag(arg0\_province, arg1\_flag\_key)

getCivilisationVariable(arg0\_civ\_tag, arg1\_variable\_key)  
getGlobalVariable(arg0\_variable\_key)  
getProvinceVariable(arg0\_province, arg1\_variable\_key)  
setCivilisationVariable(arg0\_civ\_tag, arg1\_variable\_key, arg2\_value)  
setGlobalVariable(arg0\_variable\_key, arg1\_value)  
setProvinceVariable(arg0\_province, arg1\_variable\_key, arg2\_value)  
removeCivilisationVariable(arg0\_civ\_tag, arg1\_variable\_key)  
removeGlobalVariable(arg0\_variable\_key)  
removeProvinceVariable(arg0\_province, arg1\_variable\_key)

1. **Global Scope Effects.**  
   	  
   **Meta.**  
- playMusic(arg0\_file\_path)  
- runEvent(arg0\_event\_id, arg1\_options)  
  - civ\_tags: (List\<String, CivTag\>)  
  - provinces: (Array\<String, ProvinceID\>)  
- runFunction(arg0\_function\_key, arg1\_options)  
    
  AI.  
- setAIAggression(arg0\_value)

  Diplomacy.

- createWar(arg0\_options)  
  - attackers: (List\<String, CivTag\>)  
  - defenders: (List\<String, CivTag\>)  
      
  - conquer\_vassal: (Boolean)  
  - is\_coalition: (Boolean)  
  - name: (String)  
    

  Player.  
- switchTag(arg0\_civ\_tag)  
    
  Pops.  
- createDisease(arg0\_options)  
  - disease\_type: (String, DiseaseTag)  
  - provinces: (List\<String, ProvinceID\>)


1. **International Organisation Scope Effects.**  
2. **Resource Scope Effects.**

   

- resourceChangePrice(arg0\_options)  
  - resource\_type: (List\<String, ResourceTag\>)

    

  - duration: (Number) \- The duration for the given price change in months.  
  - value: (Number) \- Value in percentage terms.  
- resourceChangePriceGroup(arg0\_options)  
- resource\_group: (List\<String, ResourceGroupTag\>)


- duration: (Number) \- The duration for the given price change in months.  
- value: (Number) \- Value in percentage terms.


2. **Civilisation Scope Effects.**

   **Economy (Civilisation).**

- civilisationAddMoney(arg0\_civ\_tags, arg1\_value)  
- civilisationAddMonthlyIncome(arg0\_civ\_tags, arg1\_value)

  **Economy (Technology).**

- civilisationAddResearchPoints(arg0\_civ\_tags, arg1\_value)  
- civilisationInstantResearch(arg0\_civ\_tags, arg1\_technology\_name)


  **Meta.**

- civilisationAddTemporaryModifier(arg0\_civ\_tags, arg1\_options)  
- id: (String)  
- name: (String)


- description: (String)  
- duration: (Number) \- The duration of the given temporary modifier in months.


- advisor\_cost: (Number)  
- advisor\_max\_level: (Number)  
- aggressive\_expansion\_modifier: (Number)  
- all\_characters\_life\_expectancy: (Number)  
- army\_maintenance: (Number)  
- army\_morale\_recovery: (Number)  
- army\_movement\_speed: (Number)  
  - \<base\_building\_category\_key\>\_buildings\_cost: (Number) \- Either ‘administrative’, ‘military’, ‘economic’, or ‘wonder’.  
- battle\_width: (Number)  
- building\_maintenace\_cost: (Number)  
- construction\_cost: (Number)  
- construction\_time: (Number)  
- core\_cost: (Number)  
- corruption: (Number)  
- devastation: (Number)  
- develop\_infrastructure\_cost: (Number)  
- diplomacy\_points: (Number)  
- discipline: (Number)  
- disease\_death\_rate: (Number)  
- economy\_income: (Number)  
  - generals\_attack: (Number)  
  - generals\_defence: (Number)  
- generals\_cost: (Number)  
- growth\_rate: (Number)  
- improve\_relations\_modifier: (Number)  
- income\_from\_vassals: (Number)  
- increase\_growth\_rate\_cost: (Number)  
- increase\_manpower\_cost: (Number)  
- increase\_tax\_efficiency\_cost: (Number)  
- inflation: (Number)  
- invest\_in\_economy\_cost: (Number)  
- loan\_interest: (Number)  
- loan\_limit: (Number)  
- loot: (Number)  
- manpower\_recovery\_from\_disbanded\_armies: (Number)  
- manpower\_recovery\_speed: (Number)  
- max\_alliances: (Number)  
- max\_amount\_of\_money: (Number)  
- max\_building\_slots: (Number)  
- max\_infrastructure: (Number)  
- max\_level\_capital\_city: (Number)  
- max\_level\_military\_academy: (Number)  
- max\_level\_military\_academy\_for\_generals: (Number)  
- max\_level\_nuclear\_reactor: (Number)  
- max\_level\_supreme\_court: (Number)  
- max\_manpower: (Number)  
- max\_manpower\_percentage: (Number)  
- max\_morale: (Number)  
  - max\_percentage\_of\_manpower: (Number)  
- max\_percentage\_of\_money: (Number)  
- military\_maintenance\_cost: (Number)  
- monthly\_income: (Number)  
- monthly\_legacy: (Number)  
- monthly\_legacy\_percentage: (Number)  
- production\_efficiency: (Number)  
- production\_income: (Number)  
- province\_maintenance: (Number)  
- recruit\_army\_cost: (Number)  
- recruit\_backline\_cost: (Number)  
- recruit\_frontline\_cost: (Number)  
- recruitment\_time: (Number)  
- regiments\_limit: (Number)  
- religious\_conversion\_cost: (Number)  
- reinforcement\_speed: (Number)  
- research: (Number)  
- research\_points: (Number)  
- revolutionary\_risk: (Number)  
- siege\_effectiveness: (Number)  
- tax\_efficiency: (Number)  
- tax\_income: (Number)  
- technology\_cost: (Number)  
- unit\_attack: (Number)  
- unit\_defence: (Number)  
- warscore\_cost: (Number)  
- civilisationRemoveTemporaryModifier(arg0\_civ\_tags, arg1\_modifier\_id)  
- civilisationScaleTemporaryModifier(arg0\_civ\_tags, arg1\_options)  
- id: (String) \- The temporary modifier ID to scale.


- duration: (Number) \- The duration in terms of months for which to scale it.  
- value: (Number, Percentage) \- What to scale it by. Base-zero percentage.


  **Military.**

- civilisationAddGeneral(arg0\_civ\_tags, arg1\_options)  
  - file: (String, FilePath.JSON)  
  - bonus\_attack: (Number)  
  - bonus\_defence: (Number)  
- civilisationAddGenerals(arg0\_civ\_tags, arg1\_value)  
- civilisationCreateArmy(arg0\_civ\_tags, arg1\_options)  
  - general: (String, FilePath.JSON)  
  - general: (Object)  
    - name: (String)  
    - attack: (Number)  
    - defence: (Number)  
    - year\_of\_birth: (Number)

      

    - image\_file: (String)  
    - image\_id: (Number)  
  - provinces: (List\<String, ProvinceID\>)  
  - \<unit\_key\>: (Number)  
  - …  
- civilisationDisbandArmy(arg0\_civ\_tags, arg1\_options)  
  - provinces: (List\<String, ProvinceID\>)  
  - value: (Number, Percentage) \- The percentage by which to disband armies  
- civilisationExpandArmy(arg0\_civ\_tags, arg1\_options)  
  - provinces: (List\<String, ProvinceID\>)  
  - value: (Number, Percentage) \- The percentage by which to expand armies.  
      
    **Politics (Internal).**  
- civilisationAddAdvisor(arg0\_civ\_tags, arg1\_options)  
  - file: (String, FilePath.JSON)  
  - value: (Number) \- The type of advisor to recruit.  
- civilisationChangeGovernment(arg0\_civ\_tags, arg1\_government\_name)  
- civilisationChangeReligion(arg0\_civ\_tags, arg1\_religion\_name)  
- civilisationSetRuler(arg0\_civ\_tags, arg1\_options)  
- name: (String)


- birth\_date: (Object, Date)  
- bonus: (Object)  
  - \<bonus\_key\>: (Value) \- See earlier add\_temporary\_modifier for more information on bonus key values.  
- death\_date: (String, Date)  
- image: (String, FilePath.PNG)  
- civilisationSetTag(arg0\_civ\_tag, arg1\_civ\_tag)


  **Provinces. \[WIP\] \- Add Civilisation Level building functions (i.e. SupremeCourt).**

- civilisationAddCapitalBuilding(arg0\_civ\_tags, arg1\_capital\_building\_key, arg2\_value)  
- civilisationAddCores(arg0\_civ\_tags, arg1\_provinces)  
- civilisationAnnex(arg0\_civ\_tag, arg1\_civ\_tags)  
- civilisationAnnexCores(arg0\_civ\_tags)  
- civilisationAnnexCoresFromCivilisation(arg0\_civ\_tags, arg1\_options)  
  - tag: (List\<String, CivTag\>)  
  - provinces: (List\<String, ProvinceID\>)  
- civilisationAnnexProvinces(arg0\_civ\_tag, arg1\_provinces)  
- civilisationAnnexProvincesFromCivilisation(arg0\_civ\_tag, arg1\_options)  
  - tag: (List\<String, CivTag\>)  
  - provinces: (List\<String, ProvinceID\>)  
- civilisationExplode(arg0\_civ\_tags)  
- civilisationMoveCapital(arg0\_civ\_tags, arg1\_provinces)  
- civilisationOccupyProvinces(arg0\_civ\_tag, arg1\_provinces)  
- civilisationOccupyProvincesFromCivilisation(arg0\_civ\_tag, arg1\_options)  
  - tag:  (List\<String, CivTag\>)  
  - provinces: (List\<String, ProvinceID\>)  
- civilisationRemoveCapitalBuilding(arg0\_civ\_tags, arg1\_capital\_building\_key, arg2\_value)  
- civilisationRemoveCores(arg0\_civ\_tags, arg1\_provinces)


3. **Province Scope Effects.**  
     
   **Economy (Building).**  
- provinceAddBuilding(arg0\_provinces, arg1\_building\_name, arg2\_value)  
- provinceRemoveBuilding(arg0\_provinces, arg1\_building\_name, arg2\_values)  
    
  **Economy (Development).**  
- provinceModifyDevastation(arg0\_provinces, arg1\_value)  
- provinceModifyEconomy(arg0\_provinces, arg1\_value)  
- provinceModifyGrowthRate(arg0\_provinces, arg1\_value)  
- provinceModifyInfrastructure(arg0\_provinces, arg1\_value)  
- provinceModifyManpower(arg0\_provinces, arg1\_value)  
- provinceModifyTaxEfficiency(arg0\_provinces, arg1\_value)  
- provinceSetDevastation(arg0\_provinces, arg1\_value)  
- provinceSetEconomy(arg0\_provinces, arg1\_value)  
- provinceSetGrowthRate(arg0\_provinces, arg1\_value)  
- provinceSetInfrastructure(arg0\_provinces, arg1\_value)  
- provinceSetManpower(arg0\_provinces, arg1\_value)  
- provinceSetTaxEfficiency(arg0\_provinces, arg1\_value)  
    
  **Economy (Pops).**  
- provinceModifyNationality(arg0\_provinces, arg1\_options)  
  - tag: (String, CivTag)  
  - number: (Number)  
  - value: (Number, Percentage)  
- provinceModifyPopulation(arg0\_provinces, arg1\_value)  
- provinceModifyPopulationPercentage(arg0\_provinces, arg1\_value)  
- provinceSetNationality(arg0\_provinces, arg1\_options)  
  - tag: (String, CivTag)  
  - number: (Number)  
  - value: (Number, Percentage)  
- provinceSetPopulation(arg0\_provinces, arg1\_value)  
- provinceSetReligion(arg0\_provinces, arg1\_religion\_name)  
    
  **Meta.**  
- provinceRenameProvince(arg0\_provinces, arg1\_province\_names)  
    
  **Politics.**  
- provinceModifyUnrest(arg0\_provinces, arg1\_value)  
- provinceSetUnrest(arg0\_provinces, arg1\_value)  
    
  1. **Building Scope Effects.**  
  2. **Pop Scope Effects.**  
     1. **Wealth Scope Effects.**
