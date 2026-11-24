<<<<<<< HEAD
# RESQGRID — EL Phase 2

RESQGRID is a community incident-reporting and resource-coordination prototype. This updated project includes separate Public and Provider workspaces, responsive sign-in screen, incident reporting, report history, incident/safety feeds, a map view, provider registration, and resource inventory snapshots.

## Important prototype limitation

The sign-in screen is **demo role selection**, not production authentication. Any valid email and a password of at least 4 characters will enter the selected workspace. There is no password verification, account database, access control, or secure user-to-provider ownership yet. Do not use real passwords or sensitive personal information. Provider inventory edits made in the browser are local to that browser; provider registration can be submitted to the API. This is a student prototype, not an official emergency service and it does not dispatch responders. In India, call **112** for emergencies.

## Requirements

- Node.js 20 or newer (Node.js 22 LTS recommended)
- npm
- Docker Desktop (recommended, for the PostGIS database) or a compatible PostgreSQL/PostGIS database

## Setup on Windows PowerShell

1. Extract this ZIP.
2. Open PowerShell in the extracted `reqgrid` folder (the folder containing the root `package.json`).
3. Install dependencies:

   ```powershell
   npm install
   ```

4. Create your local environment file:

   ```powershell
   Copy-Item .env.example .env
   ```

5. Start the PostGIS database (requires Docker Desktop running):

   ```powershell
   docker compose up -d db
   ```

6. Initialize the database schema:

   ```powershell
   npm run db:init
   ```

7. Start the API and web app in one terminal:

   ```powershell
   npm run dev
   ```

8. Open `http://localhost:5173` in your browser. The API runs at `http://localhost:4000`.

### Demo sign-in

- Select **Public login** or **Provider login**.
- Enter any valid email address.
- Enter any password with at least 4 characters.
- A name is optional. For the Provider workspace, use the same organization name you enter in the provider registration form if you want the displayed name to match.

### Running without the database

The web app still opens and displays demo incident/resource data. Report submissions and inventory snapshots can fall back to browser-local storage when the API/database is unavailable. They are not shared with other devices and should not be mistaken for database-backed records. The API/database is required for shared incident and provider records.

## Build checks

```powershell
npm run build
```

## Main features

### Public workspace
- Dashboard metrics for open/high-urgency incidents, providers, and personal report history
- Incident report form with type, location label, coordinates, urgency, people affected, and description
- My Reports list for reports created in the current browser
- Incident and provider location view with OpenStreetMap links
- Provider/resource directory with available-versus-total quantities
- Safety awareness feed generated from open incidents

### Provider workspace
- Provider registration with provider type, coordinates, resource category, and quantities
- Incident awareness feed
- Browser-local inventory snapshot entries
- Verification and data-freshness caveats

### API/database
- Existing Express API for incident and provider records
- PostGIS schema, incident assessment, live weather/facility endpoints, allocation workflow, and agent-run records from the original project

## Data and safety notes

- User reports are unverified until reviewed by an authorized coordinator.
- Provider resource quantities are self-reported and may be stale.
- OpenStreetMap facility locations do not confirm capacity or operational readiness.
- AI/agent assessment is decision support only, not official triage.
- Do not publish secrets or a real `.env` file. The ZIP intentionally includes `.env.example`, not a personal `.env` file.
=======
# RESQGRID
Emergency resource allocation management 
>>>>>>> e6e3ec754e2ea51be7e04bbfeef2f4b8c757deaf
