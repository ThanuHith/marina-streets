# Optional model packs

The game runs without external model files. It starts with hand-built low-poly cars and pedestrians plus instanced procedural city geometry, and falls back to those models whenever a manifest file is absent.

## Install the verified free packs

1. Open the official pack page and confirm it still says **Creative Commons CC0**:
   - [Car Kit](https://kenney.nl/assets/car-kit)
   - [Animated Characters Protagonists](https://kenney.nl/assets/animated-characters-protagonists)
   - [City Kit (Suburban)](https://kenney.nl/assets/city-kit-suburban)
   - [City Kit (Roads)](https://kenney.nl/assets/city-kit-roads)
2. Download each pack from its official page. Save the ZIP archives into `work/asset-downloads/` with these exact names: `kenney-car-kit.zip`, `kenney-animated-characters.zip`, `kenney-city-suburban.zip`, and `kenney-city-roads.zip`. If the site provides a direct archive URL, put that URL in the matching `downloadUrl` field in `scripts/asset-packs.json` instead.
3. Run `npm run assets:fetch`. The script extracts each archive once into `public/assets/source-packs/`; its marker files make repeat runs skip completed packs.
4. Copy the chosen low-poly models into the paths listed in `public/assets/manifest.json`, keeping the exact filenames. GLB is preferred. For an OBJ/FBX source, import it in Blender and export as glTF Binary (`.glb`); keep textures at or below 512×512.
5. Keep vehicle and character models below about 5,000 triangles each. Keep model dimensions near the collision dimensions in the manifest and make wheels easy to identify by names containing `wheel`, `tire`, or `tyre`; add `front` to the front wheel names if the model uses different meshes.
6. Run `npm run dev`. The loader caches each GLB once, plays pedestrian clips named “walk” and “idle” when present, and uses the procedural fallback for missing files.

The starter pack pages and CC0 licenses are recorded in [ASSET_LICENSES.md](ASSET_LICENSES.md). Update that file and the credits screen before using any substituted assets with attribution requirements.
