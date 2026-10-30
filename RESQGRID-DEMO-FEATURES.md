# RESQGRID demo priority and resource workflow

This prototype now adds a report summary in **Public → My Reports** after a report is submitted:

- Prototype impact score out of 100 and priority number compared with open incidents known at report time.
- Suitable resource type selection by incident type.
- Nearest demo provider with a matching resource category and positive available quantity.
- Demo request shown in **Provider → Resource Requests**.
- Provider can move request through Requested → Accepted → En route → Arrived.
- The public summary shows provider name, distance, ETA estimate, request status, and a map link to the provider's demo location.
- Demo state is saved to localStorage so public/provider demo workspaces can share it in the same browser profile.

## Important limits

Provider data and incident seed data are fictional. Priority is a transparent heuristic, not a validated emergency triage model. ETA uses straight-line distance and an assumed average speed; it is not live traffic routing. Provider location is static/simulated; this is not GPS tracking. The prototype does not contact real providers or emergency services. Real emergency services in India: call 112.

## Demo walkthrough

1. Start the project with `npm install` then `npm run dev` from the folder containing the root `package.json`.
2. Sign in to Public login using any valid demo email and a password of at least four characters.
3. Submit a sample incident (e.g. Flood, Medical, Fire, or Road blockage) with a Bengaluru location and coordinates.
4. Open **My Reports** and show the priority number, score, suitable resource, provider, distance, estimated arrival, and request status.
5. Sign out and sign in using Provider login in the same browser. Open **Resource Requests**, accept the request, mark it En route, then Arrived.
6. Sign back in to Public in the same browser and refresh My Reports to see the status updates.
