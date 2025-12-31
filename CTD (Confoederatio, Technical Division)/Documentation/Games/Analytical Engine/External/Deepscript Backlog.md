**DEEPSCRIPT BACKLOG.**

Any conditions, effects, or scopes not correctly implemented, or for which bugs have been reported, as well as known MP compatibility issues will be reported below. Problems with game polishing will also be noted. This backlog is currently being addressed.

**Effects.**

- Effects are not yet fully completed.  
    
- createWar() may not be MP compatible.  
- switchTag() does not work after game start; may not be MP compatible.

**Scopes.**

- parseEvents() sometimes do not fire for startup issues immediately after game start.

**GAME POLISH.**

- Game is slow due to daily tick events. This may have to do with parseEvents() logic over all civilisations. Consider moving to a separate async thread.  
  - PSA: Modders should use guard clause style conditions instead to boost performance.  
- MP Internal Servers used for Singleplayer Games are not fully polished on load.  
- Multiplayer tab/Chat should be hidden in internal server lobbies.  
- Re-add Hours to Game\_Calendar and possible display.  
- Sandbox mode does not work.