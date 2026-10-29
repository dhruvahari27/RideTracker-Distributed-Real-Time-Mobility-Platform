# 📱 RideTracker Frontend Client

The frontend client for **RideTracker — Distributed Real-Time Mobility & Fleet Intelligence Platform**.

Built with **React 19**, **Vite 8**, **Tailwind CSS v4**, **Zustand 5**, and **Leaflet / React-Leaflet**.

---

## 🚀 Key Modules

- **Passenger Experience (`/app/*`)**:
  - Live map view with OSRM street route rendering.
  - Multi-modal vehicle selection (Bike, Auto, Economy, Sedan, XL, EV).
  - High-precision 60 FPS driver telemetry tracking with smooth bearing interpolation.
  - Split fare calculation and instant emergency SOS panic desk.

- **Driver Partner Cockpit (`/driver/*`)**:
  - Proximity request dispatching with acceptance radar.
  - Turn-by-turn navigation stage workflow (`HEADING_TO_PICKUP` ➔ `ARRIVED` ➔ `IN_TRANSIT` ➔ `COMPLETED`).
  - Earnings tracker (88% net earnings / 12% platform fee breakdown).
  - Instant UPI withdrawal simulation.

- **Operations Command Hub (`/admin/*`)**:
  - Multi-city live vehicle radar across India (Mumbai, Delhi-NCR, Bengaluru, IIT Kharagpur, etc.).
  - Surge zones and demand/supply density heatmaps.
  - DPDP Act compliant driver contact masking and identity protection.
  - Incident triage and panic alert safety monitoring.

---

## 🛠️ Development

### Install Dependencies
```bash
npm install
```

### Start Development Server
```bash
npm run dev
```
Runs at `http://localhost:5173`. API calls to `/api/*` are automatically proxied to the backend on `http://127.0.0.1:3001`.

### Production Build
```bash
npm run build
```
Builds the optimized production client to `dist/`.

### Linter
```bash
npm run lint
```
Runs Oxlint checks across all components and pages.
