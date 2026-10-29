# COSMOS — Interactive 3D Universe

A standalone React + Three.js solar-system experience. No backend, accounts, database, or API keys required.

## Requirements

- Node.js 18.18+ (Node.js 20 LTS or newer recommended)
- npm
- A modern browser with WebGL enabled

## Run locally

1. Extract the ZIP.
2. Open a terminal in the extracted `cosmos-3d-universe` folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Open the local URL printed by Vite (normally `http://localhost:5173`).

## Production build

```bash
npm run build
npm run preview
```

The production-ready static site is generated in `dist/`.

## Current features

- Real Three.js-rendered 3D solar-system scene using React Three Fiber.
- Procedurally generated planet surface textures, with no texture downloads required.
- Clickable planets and selectable planet list.
- Mouse drag to orbit the camera and scroll to zoom.
- Planet information panel and astronomy facts.
- Orbit paths and asteroid-belt particle field toggles.
- Pause/resume planet rotation and orbit-speed presets.
- Search planets by name.
- Galaxy discovery cards and black-space visual styling.
- Settings saved to browser local storage.
- Responsive layout and reduced-motion support.

## Scope notes

- This is a front-end-only project; no backend or sign-in is included.
- Planet sizes, distances, and orbital speeds are stylized to fit a useful interactive scene and are not a scale-accurate astronomical model.
- Procedural planet textures are illustrative, not scientific surface maps.
- Galaxy cards are discovery panels, not separate interactive 3D galaxy simulations yet.
- “Free navigation” currently uses the same orbit-camera controls with a different UI state; a true first-person fly-through controller can be added as a follow-up.
- Graphics quality is currently stored as a preference label and does not yet switch renderer settings.
- Google Fonts are loaded from Google Fonts; if offline, the system font fallback is used.
- Maximum graphics uses antialiasing, up to 2x device pixel ratio, ACES tone mapping, stars, sparkles, and generated textures. On weaker devices, reduce browser zoom or adapt Canvas DPR for performance.

## Project structure

```text
cosmos-3d-universe/
├── index.html
├── package.json
├── README.md
├── public/
└── src/
    ├── App.jsx
    ├── SpaceScene.jsx
    ├── main.jsx
    ├── solarData.js
    └── styles.css
```

## Deployment

This builds to static files and can be hosted on a static host such as Vercel, Netlify, or GitHub Pages. No environment variables are needed.

## COSMOS 2.0 upgrade notes
- Cinematic opening screen with an Enter button and Skip Intro option.
- Optional ambient synth drone generated locally with the Web Audio API (no audio files or backend required). Browsers only start audio after the user presses the sound control.
- Selecting a planet now animates the camera toward it in orbit view.
- Existing planet selection, search, orbit controls, galaxy panel, preferences, and speed controls remain in place.

The visual textures are procedurally generated, not photographic NASA surface maps. For a truly photorealistic production release, add appropriately licensed high-resolution planetary maps, cloud maps, normal maps, and physically based materials. The free procedural version avoids third-party asset licensing and keeps the project frontend-only.
