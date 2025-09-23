This is a Blog of how Jenny and I built a custom map for WorkAdventure using TILED(a map editor software).

[Map Starter Kit](https://github.com/workadventure/map-starter-kit)

[Upload Map Documentation](https://docs.workadventu.re/map-building/tiled-editor/publish/wa-hosted)

Made a map with an object layer.
After attempting to upload this map i received the following error messages:

` {"floorplan_v3/floorplan_v3.tmj":{"layers":[{"type":"error","message":"
``Your map must have a layer named \"floorLayer\" of type \"Object Layer\

``".","details":"","link":"https://workadventu.re/map-building/wa-maps.md#workadventure-maps-rules"}],"tilesets":[{"type":"error","message":"
``Tilesets in TSX/TSJ format are not supported. You must embed the tilesets in the map directly.

``","details":"We detected the following tileset(s): \"../tilesets/rickyfloorplan.tsx\", \"../tilesets/colorset.tsx\".","link":"https://workadventu.re/map-building/wa-maps.md#workadventure-maps-rules"}]}}  `

I deleted the JSON map file, it apparently only needs the .tmx file(tilemap) and the tileset files.
compress it into a ZIP and upload it at workadventure.bellinghammakerspace.org/map-storage
the login credentials are found in the .env file under the map-storage section.

Now the map is uploaded successfully. Now I have to find out how to actually load it onto the game...


BACKTRACKING

starting with the [map-starter-kit docs](https://github.com/workadventure/map-starter-kit.git) these instruct me on how to setup the self hosted map storage server.
