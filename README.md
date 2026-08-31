# Extrilo Chat — Online Cloud Build

This ZIP converts the uploaded Extrilo Chat build from device-only persistence to a Firebase-backed online version.

## What changed

- Messages remain real-time through Firebase Realtime Database.
- Accounts, profiles, friends, tiers, tags, servers, promocodes, admin logs and moderators are mirrored to Firebase.
- Changes made on one browser/device are pushed to the cloud and received by other connected clients.
- Existing local data is migrated to Firebase when the cloud database is empty.
- Legacy plaintext local passwords are converted to SHA-256 hashes before cloud migration.
- Firebase Anonymous Authentication is used so the database is not exposed to unauthenticated requests.
- The theme preference remains local to the device.

## Firebase setup

The HTML already contains the Firebase project configuration from the uploaded Extrilo file.

In the Firebase Console for that project:

1. Open **Authentication → Sign-in method**.
2. Enable **Anonymous** authentication.
3. Open **Realtime Database → Rules**.
4. Use the contents of `database.rules.json`.
5. Host `index.html` from a web origin such as Firebase Hosting, GitHub Pages, Cloudflare Pages, or another HTTPS host.

Do not rely on `file://` for the final online deployment.

## Important

The Realtime Database stores the app's shared state so every connected copy sees the same servers and account directory. This is a functional cloud-sync conversion of the supplied prototype, not a production-grade Discord replacement. For a public production service, server-side authorization and stricter per-user/per-server database rules should be added.

## Files

- `index.html` — online Extrilo Chat
- `database.rules.json` — Firebase Realtime Database rules
- `firebase.json` — optional Firebase Hosting configuration
