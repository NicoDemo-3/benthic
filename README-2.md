# Tidal to Bandcamp shopping list

Sign in with Tidal, pick a playlist, and get a Bandcamp search link for every track. Tick tracks off as you buy them.

## Setup

1. Create a GitHub repo, upload `index.html`, then go to **Settings → Pages** and publish from your main branch. Note the address, e.g. `https://yourname.github.io/tidal-to-bandcamp/`.
2. At [developer.tidal.com](https://developer.tidal.com), create an app.
   - Add your Pages address as a **redirect URI**, exactly as the page shows it (trailing slash included).
   - Enable the scopes `user.read`, `playlists.read` and `collection.read`.
3. Open your Pages site, paste the app's **client ID** (no secret needed), and sign in.

To skip the client ID step, set `BUILT_IN_CLIENT_ID` near the top of the script. Client IDs aren't secret in this sign-in flow (PKCE), so it's fine to commit.

## Notes

- Everything runs in your browser. Your Tidal login token and bought ticks are stored only on your device.
- Tidal sessions last about an hour; just sign in again when prompted.
- Links open Bandcamp searches. Not every track is sold on Bandcamp.
- If Tidal's API changes, the "Or paste a track list instead" option still works with a TuneMyMusic export.
