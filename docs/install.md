# Install the widgets

Five steps, and you're glowing. Haven't set up OBS yet? Do the [basic setup](setup.md) first.

## 1. Download

Open the **[latest release](https://github.com/neongreycodes/neon-noir-stream-widgets/releases/latest)** and download, under *Assets*:

| You have | Download |
| --- | --- |
| a Mac (any, Intel or Apple Silicon) | `Neon.Noir.Stream.Widgets_…_universal.dmg` |
| a Windows PC | `Neon.Noir.Stream.Widgets_…_x64-setup.exe` |
| either | `neon-noir-stream-widgets-extension-….zip` (the browser extension) |

You need **Chrome, Edge or Brave** for the extension, and **OBS** (which you already have from the [basic setup](setup.md#a-install-obs)).

---

## 2. Install the app

The app is the heart of it all. Install it once and forget it's there.

### Mac

1. Open the `.dmg` and drag **Neon Noir Stream Widgets** into **Applications**.
2. Open it from Applications. macOS says it **can't check the app** ("unidentified developer"). That's expected, don't panic: the beta isn't registered with Apple (yet). My lawyer advised me not to comment further on Apple's paperwork. Click **Done**.
3. Open **System Settings → Privacy & Security**, scroll down, and click **Open Anyway** next to "Neon Noir Stream Widgets". Confirm with your password. You only do this once.
4. When music plays, macOS asks whether the app may **control "Music"**. Click **OK**: that's how it reads the current track.

### Windows

1. Run the `…-setup.exe`. Windows shows **"Windows protected your PC"**. That's expected for the beta: click **More info → Run anyway**.
2. Follow the installer.

On Windows there is **no music widget yet**: the chat overlay works, the now-playing card doesn't appear. It's on my list.

### Where the app lives

Closing the settings window does **not** stop the app (that's on purpose): it keeps running in the background so your overlays keep working. To get the window back or to quit, click the **NG** icon:

- **Mac:** in the menu bar at the top right (clicking the app's Dock icon also opens the window).
- **Windows:** in the system tray at the bottom right (maybe behind the **^** arrow).

It offers **Open settings** and **Quit**.

---

## 3. Install the browser extension

The extension is your little spy in the chat. A friendly one.

1. Unzip `neon-noir-stream-widgets-extension-….zip`. You get a folder **neon-noir-stream-widgets-extension**. Put it somewhere it can stay (e.g. your Documents). **Don't delete it later**: the browser loads the extension from there.
2. In the browser, open `chrome://extensions` (Edge: `edge://extensions`, Brave: `brave://extensions`).
3. Turn on **Developer mode** (a switch: top right in Chrome and Brave, on the left in Edge).
4. Click **Load unpacked** and choose the **neon-noir-stream-widgets-extension** folder.
5. Click the puzzle piece in the toolbar and **pin** Neon Noir Stream Widgets, so its icon is always visible.

---

## 4. Set it up

![Switching to Neon Noir Light in the app's Overlay tab, with a 5-star rating banner on stream](../images/theme-select-beta.jpg)

Open the app's settings (NG icon → **Open settings**). The beta notice no longer jumps at you on every start; if you miss it, **About** (bottom right) shows it.

The window has two views, switched at the top: **Settings** (who you are and how everything connects) and **Features** (what shows up on your stream). Toggles and dropdowns save the moment you touch them. Only typed text (username, triggers, dares) has a **Save** button, and it turns into **"✓ Saved"** so you know it worked.

**In Settings:**

1. **Chat username:** your name on the chat site, then **Save**. The app needs it to recognise *your* slot spins, dice rolls, ratings and tip menu requests.
2. **Your avatar:** the app grabs it from your cam site profile by itself. If it can't find one, it tells you why right there.
3. **Browser extension:** the app shows a pairing code like `K7QM-4XPA` (there's a **Copy** button). Click the extension icon in the browser, type the code and click **Pair**. The popup now says **Connected to the app**, and the app says **Connected**. While nothing is connected, a little dot sits on the Settings tab to nag you.
4. **Browser Source URL:** the address for OBS, with a **Copy** button. You need it in [step 5](#5-add-it-to-obs).
5. **Overlay theme:** pick the look you like; **Neon Noir Dark** is the default. It changes in OBS within 2 seconds.

The pairing code makes sure only *your* extension can send events to your overlays. Nobody else gets to throw confetti on your stream.


**In Features**, every part of the overlay has its own switch. What they all do is in [Features](features.md#the-features-view).

---

## 5. Add it to OBS

Time to see it glow.

1. In your scene, add a **Browser** source (on top of your webcam).
2. **URL:** `http://localhost:8787/neonnoirwidgets/` (or just hit **Copy** in the app's Settings view)
3. **Width** `1920`, **Height** `1080`.
4. OK.

That one source shows everything you switched on in Features. One source, done, no fiddling.

> **Coming from an older version?** The separate chat and music sources are gone. If you still have `http://localhost:8787/chat/` or `http://localhost:8787/music/` in OBS, delete them and use the one address above instead.

The app must be running while you stream. Without it, the browser source stays empty. Because you're sending OBS out as your virtual webcam (see the [basic setup](setup.md#b-turn-obs-into-your-webcam)), the widgets now show up on the site too.

---

## Updates

I keep improving things, so check back now and then. When a new version is out, the app's settings window and the extension popup show **"Update available"**. Always update **both** the app and the extension, they like to be on the same version. Then:

- **App:** download the new `.dmg` / `-setup.exe` from the [latest release](https://github.com/neongreycodes/neon-noir-stream-widgets/releases/latest) and install it over the old one. Your settings stay.
- **Extension:** unzip the new extension and replace the **contents** of your extension folder with it. Then open `chrome://extensions` and click the **reload** arrow on the extension.

---

[← Back to the start](../README.md) · [← The basic setup](setup.md) · [Next: Features →](features.md)
