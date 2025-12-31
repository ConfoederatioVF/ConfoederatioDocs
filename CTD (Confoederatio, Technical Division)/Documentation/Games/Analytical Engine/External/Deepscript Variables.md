**Logic (Variables).**

**Variables** can be assigned to local **Logic (Scopes)** within **Analytical Engine** parsing and are used to store various flexible values. **Variable Operations** can also be performed on Variables such that complex mathematical equations can be given to them; these can also be done in String resolutions for Numbers.

The types of variables are mainly restricted to Arrays, Flags, Objects, Numbers, and Strings \- all of which are processed in JS using **Nashorn**, allowing for more flexible variable expression which can be used in both localisation as well as Custom UIs. Variable effects are noted below.

Values are evaluated utilising **Nashorn**.

**Formatting/Value Functions.**

parseDisplayLocalisationString(arg0\_string, arg1\_options)  
parseVariableString(arg0\_string, arg1\_options)

**Data Structure.**

main: (Object)

- gamestate: (Object)  
  - global: (Object)  
  - civilisations: (Object)  
    - \<civ\_tag\>: (Object)  
  - provinces: (Object)  
    - \<province\_id\>: (Object)