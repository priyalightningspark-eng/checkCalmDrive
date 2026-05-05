# CalmDrive 🚗

A Progressive Web App that helps prevent road rage by detecting stress triggers (sudden motion, voice spikes) and playing calming cues through your car's Bluetooth speakers.

## Features
- 🎙 Microphone volume monitoring — detects yelling / loud honking
- 📱 Accelerometer monitoring — detects sudden braking or acceleration
- 🔔 Soft chime + voice cue: *"Pause. Breathe. Stay in control."*
- 📊 Drive summary: motion triggers, voice spikes, cues played
- 📲 Installable to home screen (PWA)
- 🔒 Privacy-first: no audio stored, all processing on-device
- 🔵 Bluetooth-ready: audio routes to car speakers automatically

---

## Deploy to GitHub Pages (free, 5 minutes)

### 1. Create a GitHub account
Go to [github.com](https://github.com) and sign up if you don't have one.

### 2. Create a new repository
- Click **New repository**
- Name it: `calmdrive` (or anything you like)
- Set it to **Public**
- Click **Create repository**

### 3. Upload the files
Upload these files to the repo root:
```
index.html
manifest.json
sw.js
icons/
  icon-192.png
  icon-512.png
```

### 4. Enable GitHub Pages
- Go to your repo → **Settings** → **Pages**
- Under "Source", select **Deploy from a branch**
- Choose **main** branch, **/ (root)** folder
- Click **Save**

### 5. Your app is live!
In ~1 minute your app will be at:
`https://YOUR-USERNAME.github.io/calmdrive/`

Share that URL — users on Android can install it from Chrome. On iPhone, open in Safari → Share → "Add to Home Screen".

---

## Add GA4 Analytics (optional)

1. Go to [analytics.google.com](https://analytics.google.com)
2. Create a new property → get your **Measurement ID** (looks like `G-XXXXXXXXXX`)
3. Open `index.html`, find this line near the top of the `<script>`:
   ```js
   const GA_ID = '';
   ```
4. Paste your ID:
   ```js
   const GA_ID = 'G-XXXXXXXXXX';
   ```

Events automatically tracked:
- `drive_start` — user taps Start Drive
- `drive_end` — user ends drive (includes trigger counts)
- `motion_trigger` — sudden acceleration/braking detected
- `voice_spike` — loud voice/sound detected
- `cue_played` — calming cue fired

---

## App Icons

The `icons/` folder needs two PNG files:
- `icon-192.png` — 192×192px
- `icon-512.png` — 512×512px

You can create a simple green circle with a car emoji using any image editor, or use a free tool like [favicon.io](https://favicon.io).

---

## Permissions required
| Permission | Why |
|---|---|
| Microphone | Detects voice spikes and loud sounds |
| Motion sensors | Detects sudden braking / acceleration |
| Screen wake lock | Keeps screen on while driving |

No audio is ever recorded or stored. Detection runs entirely on-device.

---

## Known limitations
- **iOS Safari**: Microphone works, but background audio may pause if the screen locks (use the screen wake lock feature). Motion sensors require a tap permission prompt on iOS 13+.
- **Android Chrome**: Full support including background operation.
- Motion detection accuracy depends on how the phone is mounted.
