[README.md](https://github.com/user-attachments/files/33361292/README.md)
# DPro — Intelligent Security Drone App

A responsive, zero-build **prototype dashboard** for the DPro triangular tricopter security drone.

> **Simulation only:** This repository does not fly a drone, display a live camera feed, perform AI detection, or communicate with aircraft hardware. All buttons and metrics currently operate on local demonstration state.

## Features (v1.0)

- Responsive desktop/mobile drone operations dashboard
- Simulated battery level, altitude, flight duration and aircraft status
- Launch, land and return-to-dock **simulation** controls
- Explicit flight confirmation and demo low-battery auto-land behavior
- Simulated security event button and session activity log
- Camera placeholder clearly labeled **NO LIVE VIDEO**
- No backend, no credentials, no required npm packages

## Run locally

Open `index.html` in a browser, or run a local static server:

```bash
python -m http.server 8080
```

Visit `http://localhost:8080`.

## Deploy with GitHub Pages

1. Upload all three files (`index.html`, `styles.css`, `app.js`) to the repository root.
2. In GitHub, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Open the URL GitHub Pages provides after deployment.

## Project structure

```text
DPro/
├── index.html     # Accessible application layout
├── styles.css     # Dark responsive dashboard theme
├── app.js         # Local simulation and UI event handling
└── README.md      # Project setup and roadmap
```

## Suggested integration roadmap

1. **Authentication & backend:** add authenticated API with role-based authorization, rate limiting, audit logging and server-side secret storage. Keep API keys out of GitHub and browser JavaScript.
2. **Telemetry:** fetch or subscribe to validated drone telemetry through a trusted backend transport; distinguish stale data and disconnections.
3. **Video:** provide authenticated WebRTC sessions via a gateway such as LiveKit/MediaMTX; handle camera and network failures clearly.
4. **Drone commands:** introduce explicit command validation, secure command acknowledgement, hardware flight-controller integration and fail-safe behavior. Follow applicable airspace and privacy laws. Never use web UI state as the flight safety authority.
5. **AI alerts:** process events on a backend, store only necessary data, and provide human review before any consequential response.
6. **Mobile app:** package a tested secure web frontend as a PWA or native React Native/Expo application if needed.

## Important safety note

Before any real flight capability is enabled, implement geofencing, physical emergency stop and manual override paths, loss-of-link fail-safes, low-battery return/land behavior, preflight hardware checks, command authentication and testing under controlled conditions. This frontend is **not** flight-control software.
