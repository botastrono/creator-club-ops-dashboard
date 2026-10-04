CREATOR CLUB OPERATIONS DASHBOARD

Purpose
- One public, read-only view of team missions, QA, blockers, stalls, launch gates, experiments, and Matt decisions.
- Discord remains the team conversation. status.json is the dashboard source of truth until a persistent update API is deployed.

Local preview
  cd creator-club-ops-dashboard
  python3 -m http.server 4173
  open http://127.0.0.1:4173

Update workflow
- Edit status.json with the latest mission or event state.
- updatedAt and each changed mission updatedAt must use ISO 8601 UTC timestamps.
- Never place credentials, private member data, email addresses, or personal notes in status.json.
- The UI refreshes status.json every 60 seconds and marks active missions stalled after two hours without an update.

Deployment
- Static Vercel project. No build command is required.
- Vercel CLI authentication or a linked Git repository is required for first deployment.
