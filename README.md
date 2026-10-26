# Trip Planner — sign-in pages

Static pages served at https://trip.mariogrebelski.com by GitHub Pages.

- `oauth/consent/` — the OAuth consent screen for the Trip Planner MCP
  connector. Supabase Auth (the authorization server) sends the browser here
  with `?authorization_id=…` when Claude asks to connect; the page signs the
  traveller in and approves or denies.
- `claude/` — the setup guide to share with travellers: one URL to copy
  and the steps to add Trip Planner as a Claude connector.
- `index.html` — a short note at the Supabase Auth Site URL, which exists
  only to prefix the consent path. Accounts, invites and passwords are all
  handled in the iOS app.
- `robots.txt` and a `noindex` tag on every page keep these out of search
  results. They're meant to be shared by link, not found.

Nothing here is secret: the Supabase key in the consent page is the
publishable key, which is public by design; access is enforced by Supabase
Auth and row-level security. The app and the `trip-agent` function live in
the private `europe-trip` repository.
