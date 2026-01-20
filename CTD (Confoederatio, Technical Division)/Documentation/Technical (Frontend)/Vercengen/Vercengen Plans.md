---
cover: https://i.postimg.cc/J7SgyNxT/embed-template-vercengen.png
description: Roadmap and planning outlines for Vercengen, particularly for Components.
---
#vercengen #plans #TODO

The following is a list of plans that represent the continuous roadmap for [[Vercengen]].

| Plan                           | Type      | Status | Date             |
| ------------------------------ | --------- | ------ | ---------------- |
| [[Vercengen 0.95b Ghassulian]] | General   | WIP    | 24 December 2025 |
| [[Vercengen Polish 1]]         | General   | WIP    | 22 December 2025 |
| [[Vercengen DatavisSuite]]     | Component | WIP    | 21 December 2025 |
| [[Vercengen NodeEditor]]       | Component | DONE   | 19 December 2025 |
### Post-release Caveats

The following concerns should ideally be addressed after a **1.0** release of Vercengen as it currently stands.

- Localisation catchup by supporting UN+1 languages (official languages of the UN and German).
- Missing components: 
	- ve.3DEditor, ve.AgentBrowser, ve.AudioEditor, ve.AudioPlayer, ve.Chatroom, ve.Datavault (Node.js only), ve.GIS (Node.js only), ve.ImageEditor, ve.JSONEditor, ve.MediaGallery, ve.RemoteControl, ve.VideoEditor, ve.VideoPlayer, ve.VirtualMachine, ve.WebsiteBuilder, ve.Wiki
- Simplify Hierarchy by adding streamlined optioning for drag and synchronisation behaviour, as well as the ability to create new list items/groups.
- Single-file CDN:
	- Address non-component incompatibility issues and global namespace (window.global)
	- `autopack.bat`/`autopack.sh` for managing `<script>` and `<link>` concatenation.
	- Pseudo fs binding/file system using localStorage for `ve.File`/`ve.FileExplorer`.

Last updated: 23 December 2025