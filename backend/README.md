# ⚙️ RideTracker Backend Service

The high-concurrency API service and telemetry hub for **RideTracker — Distributed Real-Time Mobility & Fleet Intelligence Platform**.

Built with **Node.js (ESM)**, **Express 4**, embedded **SQLite** with persistent JSON disk mirroring, **PostgreSQL** pool support, and design stubs for **Apache Kafka**, **Redis GEO**, and **Apache Flink** stream processing.

---

## 🚀 Key Features

- **Multi-Role Authentication**: JWT-based authentication for Passengers (`USER`), Drivers (`DRIVER`), and Operations Administrators (`ADMIN`).
- **Zero-Config Persistent Storage**: Embedded SQLite engine (`backend/data/ridetracker.db`) + persistent disk mirror (`backend/data/store.json`) with automatic pre-seeded demo accounts.
- **PostgreSQL Ready**: Enterprise connection pool and full DDL schema (`src/db/schema.sql`).
- **Telemetry & Stream Stubs**:
  - Apache Kafka producers for `ride.requested`, `driver.gps`, and `pricing.updated`.
  - Redis GEO index queries for sub-millisecond driver proximity lookup.
  - Apache Flink tumbling window simulation for demand/supply surge calculation.
- **DPDP Act Compliance**: Helper functions for one-click contact masking and privacy-preserving data exports.

---

## 🛠️ Development

### Install Dependencies
```bash
npm install
```

### Start Server
```bash
# With nodemon auto-reload:
npm run dev

# Standard node start:
npm start
```
Server listens on `http://127.0.0.1:3001`.

### Endpoints Overview

- `GET  /health` — Health check & database diagnostics
- `POST /api/v1/auth/signup` — Create user/driver/admin account
- `POST /api/v1/auth/login` — Sign in and receive signed JWT
- `GET  /api/v1/rides/active` — Active ride telemetry state
- `POST /api/v1/rides/request` — Create ride dispatch
- `GET  /api/v1/drivers` — Available drivers near coordinates
- `GET  /api/v1/locations/search` — Indian location & landmark lookup
- `POST /api/v1/pricing/estimate` — Dynamic fare estimation with surge
- `GET  /api/v1/analytics/overview` — Operational telemetry metrics
- `POST /api/v1/incidents/report` — SOS panic trigger dispatch
