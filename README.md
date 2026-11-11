# Marina Streets

Marina Streets is a small, original third-person coastal city game made with Three.js, Vite, and plain JavaScript modules. Explore the streets, take a car, ride the Harbor Circuit, or roam after the race. The world and its current models are generated locally from lightweight primitives; no game assets are fetched while playing.

## Play on your computer

Install [Node.js 22](https://nodejs.org/), open a terminal in this folder, and run:

```sh
npm ci
npm run dev
```

Open the local address Vite prints. To verify the production build locally:

```sh
npm run build
npm run preview
```

## Publish as a playable GitHub Pages site

The repository includes a GitHub Actions workflow. After you push the project to a repository whose default branch is `main`:

1. Open the repository on GitHub and go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. Open **Actions** and wait for **Build and publish Marina Streets** to finish.
4. Share the Pages URL shown in **Settings → Pages**. For a repository named `marina-streets`, it will be `https://YOUR-USERNAME.github.io/marina-streets/`.

The workflow rebuilds and republishes the game on each push to `main`. Vite is configured with relative asset paths so the game also loads under GitHub Pages' repository subpath.

If this folder is not already a Git checkout, create a **public** repository on GitHub named `marina-streets`, then run these commands here (replace the URL with the one GitHub shows):

```sh
git init -b main
git add .
git commit -m "Publish Marina Streets game"
git remote add origin https://github.com/YOUR-USERNAME/marina-streets.git
git push -u origin main
```

Do not add `node_modules` or `dist`; they are ignored. GitHub Actions installs dependencies and creates the deployable `dist` build for you.

## Controls

**Keyboard and mouse:** WASD move/steer, Shift run/drift, Space jump/brake, E enter or exit a vehicle, mouse drag orbit camera, Escape pause, F3 toggle FPS. Click **Start Exploring**, get into one of the three cars, and accept the race in the red ring. The Harbor Circuit has four cars and three laps.

**Touchscreens:** use the on-screen direction pad to walk or steer, **E** to enter/exit, **Jump / Brake**, and **Run / Drift**. Drag on the open game view to orbit the camera. Tap the pause icon for the menu.

Choose Low or Medium graphics from the pause menu. Low keeps the streamed world and nearby traffic/pedestrian counts small. Engine audio begins after interaction, following browser audio rules.

## Project structure

`src/main.js` starts the game. `src/game.js` coordinates input, camera, and rendering. `player.js`, `vehicle.js`, `race.js`, `road.js`, `traffic.js`, `world.js`, `chunks.js`, `pedestrians.js`, `ui.js`, `audio.js`, and `config.js` hold the gameplay systems. `public/assets/manifest.json` describes optional CC0 model packs; procedural models remain the default fallback. See [ASSET_LICENSES.md](ASSET_LICENSES.md) and [ASSETS_HOWTO.md](ASSETS_HOWTO.md) before adding external models.
