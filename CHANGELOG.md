# Changelog

## Visitor-ready publishing

- Added touchscreen movement, driving, vehicle interaction, and touch-drag camera controls.
- Added GitHub Pages build-and-deploy automation and relative asset paths for repository hosting.

## Harbor Circuit race flow and world traffic

- Expanded the three-lap circuit to a 200 m square loop and enlarged the red start circle.
- Added a floating arrow that points toward each next checkpoint and zoomed the minimap out to show the whole route over the street grid.
- Added an always-visible checkpoint compass cue with live distance, so the next turn remains readable beyond the camera's draw distance.
- Kept ambient traffic active during races; traffic picks turns at intersections and is constrained to the road network.
- Enabled entering, exiting, and switching between the three driveable cars during a race while retaining the player's lap progress.
- Opponents now park off the road after finishing or after the player completes the race. Added a final place screen with Race Again and Continue Roaming options.

## Camera and race map polish

- Camera now trails the character or car's travel heading, looks ahead, and eases back with speed-aware distance while keeping mouse orbit.
- Moved the opening area beside the road and brought capped ambient traffic closer so road vehicles are visible early.
- Replaced the generic minimap grid with the street network, highlighted race loop, labeled start/finish, and live colored opponent dots.

## Harbor Circuit race

- Replaced the mission selector with one red start zone and a four-car, three-lap race.
- Added a three-second grid countdown, lap and position HUD, AI racers on the road grid, and road-only ambient traffic.
- Added oriented car-to-car and car-to-building collision checks; parked vehicles remain stationary when hit.
- Kept the three original selectable vehicle types and existing pedestrian/camera systems.

## Asset integration preparation

- Added a manifest-driven GLB loader with caching, missing-file fallbacks, and a loading screen.
- Added detailed procedural low-poly vehicle and pedestrian fallbacks, including wheel spin, front-wheel steering, pedestrian walk motion, and near-player animation mixers for optional animated GLBs.
- Added four verified CC0 Kenney pack records, a repeat-safe archive fetch/extract script, setup instructions, and an in-game credits panel.
- Preserved the existing driving, player movement, collision resolver, mission flow, and minimap code paths.
- External models were not downloaded in this environment; the game currently runs entirely on procedural fallbacks.
