Hospital Reservation System

A React + Vite web app for booking hospital appointments, with a patient-facing
booking flow and a staff dashboard for managing doctors and reservations.

## Features

- **Patient view**: browse doctors by department, pick a date and time slot,
  submit contact details, and receive a ticket-style confirmation with a
  reservation code.
- **Staff view**: an overview of today's/this week's reservations, a
  searchable/filterable reservations table (confirm, cancel, delete), and a
  doctor roster manager (add/remove doctors).

All data lives in React state for this demo — no backend or database is
wired up yet. See "Connecting a backend" below for next steps.

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL (typically http://localhost:5173).

## Build for production

```bash
npm run build
npm run preview
```

## Project structure

```
src/
  data/seed.js         design tokens, departments, seed doctors/appointments
  lib/helpers.js        date, scheduling and code-generation helpers
  components/           one component per file (doctor cards, booking panel,
                         ticket stub, staff dashboard tabs, etc.)
  App.jsx                app shell: header, patient/staff toggle
  main.jsx                React entry point
  index.css               fonts + base styles
```

## Connecting a backend

To make this a real reservation system you'll want to:

1. Replace `src/data/seed.js` seed arrays with API calls (e.g. `fetch` or a
   library like `axios`/`swr`) to a backend (Node/Express, Django, Rails,
   Supabase, Firebase, etc.).
2. Move `doctors` / `appointments` state in `App.jsx` into a data-fetching
   hook, and make `setAppointments` / `setDoctors` call your API instead of
   only updating local state.
3. Add authentication for the Staff view (currently it's just a UI toggle,
   with no access control).
4. Persist reservations in a real database and add server-side validation
   (double-booking checks, required fields, etc.).

## License

MIT — feel free to adapt this for your own project.
