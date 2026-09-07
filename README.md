# Extrilo Chat — Online Cloud Build

This ZIP converts the uploaded Extrilo Chat build from device-only persistence to a Firebase-backed online version.

## What changed

🚀 Extrilo Chat v2 — Major Update
💬 Direct Messages
Added real 1-to-1 DMs
DM users using their unique Extrilo ID
Messages are sent to the selected user instead of a random account
Added DM interface and conversation handling
👤 Profiles
Click a user's name in chat to open their profile
Profile now shows:
Bio
Social link
Favourite game
Account age
Current plan/tier
Owned servers
Improved profile customization
🎨 Usernames & Fonts
More animated username styles
Added additional animation types
Added more fonts, including:
Gothic / Old English
Garamond
Palatino
Lucida Console
Times New Roman
Comic Sans
Copperplate
Fantasy
Cursive
VIP+ users can customize their username appearance
🔨 Moderation
Mute now actually works
Muted users are prevented from sending messages
The message box remains usable, but messages are blocked while muted
Supporter users can mute for up to 30 seconds
SynapseX users get advanced moderation abilities
Added/improved kick and mute controls
🖼️ Supporter Tier

New Supporter plan:

Mute users up to 30 seconds
Bypass image/picture cooldown
⚡ SynapseX Tier

New SynapseX plan:

5 free random promo codes
Secret promo-code vault
JavaScript terminal
Mute users
Kick users
Create tag promo codes
Access to SynapseX-only server
Create custom server bots
Create custom server commands
🏠 Custom Servers
Improved channel management
Add channels
Remove channels
Better server customization
Server-specific commands
Server-specific bots
SynapseX-exclusive server
🤖 Custom Bots
SynapseX users can create their own server bots
Custom bot names and settings
Bots can respond to server activity/commands
⚙️ Custom Commands
SynapseX server owners can create custom commands
Commands can perform JavaScript actions
Commands are stored per server
🎟️ Promo Codes
Added Supporter + SynapseX tiers to the promo system
SynapseX reward system
Tag promo-code creation
Secret promo-code vault
🔐 Tier System

Added two new tiers:

Supporter

Image cooldown bypass + limited moderation

SynapseX

Advanced moderation + terminal + vault + bots + commands + exclusive server

🛠️ Technical
Expanded Firebase cloud-state storage
Added DM data storage
Added profile metadata
Added vault storage
Added server command storage
Added server bot storage
Improved moderation enforcement
Improved profile rendering
Improved tier handling
Updated Firebase integration
📌 v2 Focus

More customization. More control. More social features. More power for server owners.

Extrilo Chat v2 — Built for customization.

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
