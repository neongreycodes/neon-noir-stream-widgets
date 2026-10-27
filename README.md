![Neon Noir Stream Widgets on stream: tip banner with confetti, latest tip and rating, the now-playing card, and the app's Overlay tab](images/opener-beta.jpg)

# Neon Noir Stream Widgets (beta)

Hey, I'm **Neon Grey** 💜 I stream on **webcammodels.com / cammedia.com**, and at some point I got tired of my stream looking like every other stream. So I built myself a little neon toolbox. It worked so well that I'm sharing it with you.

Here's the idea in three sentences:

1. **Better picture.** Instead of handing the site your raw webcam, you let **OBS** build your stream and send it out as a **virtual webcam**. Same camera, same room, but suddenly you get lighting tweaks, crops, scenes and overlays, and your whole stream just looks *better*.
2. **The browser extension listens.** It sits in your browser next to the chat and passes everything that happens there (tips, ratings, slot spins, dice rolls, tip menu requests, and the room chat if you want it on stream) on to the app. Bonus: it also asks your camera for 1080p and switches off the voice filter, so your music comes through clean instead of sounding like a phone call.
3. **The app puts on the show.** The overlay app (for **macOS and Windows**) runs quietly in the background and serves little local web pages with all the widgets. You add them to OBS as a browser source, and they light up right on your stream.

> **🔒 Your stuff stays yours.** No accounts, no tracking, no analytics. The app and the extension don't collect or send anywhere what you or your viewers do. Everything runs locally on your computer: the extension talks only to the app (via `localhost`), and the app talks only to OBS. Only two little things go online: a peek at this GitHub page (when the app starts and every 6 hours) to see if there's an update, and (Mac) when a song has no cover art, the app asks Apple's iTunes search for one using just the song title and artist.
>
> *My lawyer just cleared his throat, so: this describes what the app does, it is no legal promise in the actual sense.*

### What lights up on your stream

- **Chat events with faces:** banners for tips and 5-star ratings, now with the sender's avatar, and it's *alive*: it pops in, gets more coins the bigger the tip, and a 5-star rating gets stars orbiting around it. Plus your latest rating and tip, slot machine and dice animations with confetti (lots of confetti), and your own avatar beside the panel, hoping, cheering and shaking its head when it's a miss. No avatar? Then a neon disc with the first letter of the name shows up instead.
- **Dare Wheel:** a viewer tips for your tip menu item (e.g. "Spin my Dare Wheel") and *you* are the dial: your six dares orbit your avatar, a light beam circles your ring and lands on one, and the winning dare rises in under you.
- **Dice Duel:** a viewer tips for your Dice Duel item and plays against you. Two dice each, higher sum wins the round, first to 3. Viewer wins: they get the action you set. You win: "Good luck next time". Muahaha.
- **Tip Action Teaser:** a little side pill with your avatar that tells everyone what's on your tip menu ("Spin my Dare Wheel", "Play Dice Duel against me", "See all my rewards").
- **Be right back:** one click and your stream gets a full-screen away screen with your avatar and the song that's playing. Tips and Dare Wheel spins wait politely and play one after another when you're back. Want more? Turn it into a live room chat so your viewers keep talking while you pee. Sorry. While you *powder your nose*.
- **Room chat on stream:** a chat box above "Latest Tip", with avatars, names and the site's emojis.
- **Now playing** (macOS only): the current Apple Music track with its cover and a progress bar.
- **Themes:** Neon Noir Dark (the default, neon at night) and Neon Noir Light (the same street by day). Behind the banners, cards and games there's a slowly scrolling neon grid now, very 80s, and way lighter on OBS than the old GIF backgrounds ever were.
- **HD webcam + clean audio:** thanks to the extension, see above.

Everything has its own on/off switch, so you only show what you want.

> **Windows friends:** Windows is still **experimental**. The app installs and connects to the extension, but I haven't fully tested the overlays on Windows yet, and there's no music widget there yet. If you're on Windows, your feedback helps me the most.

> **This is a beta.** Things may still break, and that's okay, that's what betas are for. If something acts weird or you have an idea, tell me: DM me on webcammodels.com when I'm online, send Fan Mail when I'm offline, or open a [GitHub issue](https://github.com/neongreycodes/neon-noir-stream-widgets/issues). The log helps me a lot (see [Troubleshooting](#troubleshooting)). Thanks for testing! 🖤

### Talk to me 💬

I'm curious about everything: what works, what feels clunky, where setup got you stuck, what you think of the colours, fonts and animations on stream, and which widget you'd love to see next. Using a widget on your stream? Show me, I'd love to see it! 💜

- **Found a bug?** Open an [issue](https://github.com/neongreycodes/neon-noir-stream-widgets/issues).
- **Ideas, questions, show and tell?** Come hang out in [Discussions](https://github.com/neongreycodes/neon-noir-stream-widgets/discussions).
- No question is too small, and beginners are very welcome. Be kind and open-minded: everyone is welcome here, whoever you are. 🌈

---

# Part 1: The basic setup

Before the widgets, let's get the stage ready. You do this once, then it's just there.

## A. Install OBS

OBS is free, and it's what turns your webcam into a proper stream.

1. Download it from **[obsproject.com](https://obsproject.com)** (macOS or Windows) and install it.
2. Open it. If the auto-configuration wizard pops up, pick **Optimize just for virtual camera**, or close it and continue below.
3. Open **Settings → Video** and set **Base (Canvas) Resolution** and **Output (Scaled) Resolution** to `1920x1080`. That matches the widgets and the 1080p the extension asks for.
4. In your scene, add a **Video Capture Device** source and pick your webcam. Make it fill the canvas (right-click → **Transform → Fit to screen**).

## B. Turn OBS into your webcam

1. In OBS, click **Start Virtual Camera** (in the **Controls** dock, bottom right).
2. **Mac only, first time:** macOS asks to allow the OBS camera extension. Say yes, and if it sends you to **System Settings**, allow it there and restart OBS. Then click **Start Virtual Camera** again.
3. On the chat site, open your broadcast settings and pick **OBS Virtual Camera** as your camera.

Now whatever OBS shows is what your viewers see, widgets included once you've added them in [Part 2](#5-add-it-to-obs). OBS has to stay open with the virtual camera running while you stream.

## C. Music on your stream (macOS)

Want your Apple Music playing in the background of your show? (Anything goes. Except Madonna. She's cryo-frozen until her next show anyway, let her rest.) The trick: route it through a **virtual audio device** and let the site use that device as your **microphone**.

Heads up: this is **pure music, no voice**. That's my setup and it's what I use. If yours looks different, you'll have to figure that part out yourself. 😉

> **My comfy tip:** use an **external Bluetooth speaker with its own volume knob**. This audio routing switches off the macOS volume control, so otherwise the only way to make it quieter in your room is to turn it down in Apple Music, and that turns it down for your viewers too. With a speaker you set your room volume on the speaker, and the stream stays happy.
>
> *This is no audio-engineering advice in the actual sense.*

1. Install **[Background Music](https://github.com/kyleneideck/BackgroundMusic)** (free). It adds a virtual audio device called **Background Music**.
2. Open the **Audio MIDI Setup** app (Applications → Utilities). Click **+** at the bottom left → **Create Multi-Output Device**, and tick **Background Music** plus the speaker you want to hear it on (your Bluetooth speaker, or the internal speakers).
3. Open **System Settings → Sound**. Under **Output**, pick the new **Multi-Output Device**. Under **Input**, pick **Background Music**.
4. In Chrome, on the chat site, pick **Background Music** as your **microphone**.

Now your music plays in your room *and* goes straight into your stream. Keep the browser extension running: it switches off the browser's voice filtering, which otherwise squashes music into something tinny. With it, your playlist sounds the way it should. 🎶

---

# Part 2: Install the widgets

## 1. Download

Open the **[latest release](https://github.com/neongreycodes/neon-noir-stream-widgets/releases/latest)** and download, under *Assets*:

| You have | Download |
| --- | --- |
| a Mac (any, Intel or Apple Silicon) | `Neon.Noir.Stream.Widgets_…_universal.dmg` |
| a Windows PC | `Neon.Noir.Stream.Widgets_…_x64-setup.exe` |
| either | `neon-noir-stream-widgets-extension-….zip` (the browser extension) |

You need **Chrome, Edge or Brave** for the extension, and **OBS** (which you already have from [Part 1](#a-install-obs)).

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

![Switching to Neon Noir Light in the app's Overlay tab, with a 5-star rating banner on stream](images/theme-select-beta.jpg)

Open the app's settings (NG icon → **Open settings**). The beta notice no longer jumps at you on every start; if you miss it, **About** (bottom right) shows it.

The window has two views, switched at the top: **Settings** (who you are and how everything connects) and **Features** (what shows up on your stream). Toggles and dropdowns save the moment you touch them. Only typed text (username, triggers, dares) has a **Save** button, and it turns into **"✓ Saved"** so you know it worked.

**In Settings:**

1. **Chat username:** your name on the chat site, then **Save**. The app needs it to recognise *your* slot spins, dice rolls, ratings and tip menu requests.
2. **Your avatar:** the app grabs it from your cam site profile by itself. If it can't find one, it tells you why right there.
3. **Browser extension:** the app shows a pairing code like `K7QM-4XPA` (there's a **Copy** button). Click the extension icon in the browser, type the code and click **Pair**. The popup now says **Connected to the app**, and the app says **Connected**. While nothing is connected, a little dot sits on the Settings tab to nag you.
4. **Browser Source URL:** the address for OBS, with a **Copy** button. You need it in [step 5](#5-add-it-to-obs).
5. **Overlay theme:** pick the look you like; **Neon Noir Dark** is the default. It changes in OBS within 2 seconds.

The pairing code makes sure only *your* extension can send events to your overlays. Nobody else gets to throw confetti on your stream.

**In Features**, every part of the overlay has its own switch: tip and rating banners and cards, Dice Roll and Slot Spins, the music player (on stream and on Be right back), the tip actions, the teaser and the room chat. Switch something off and OBS follows at once, and the cards at the bottom left close the gap. A card with a **pink border** is on.

---

## 5. Add it to OBS

Time to see it glow.

1. In your scene, add a **Browser** source (on top of your webcam).
2. **URL:** `http://localhost:8787/neonnoirwidgets/` (or just hit **Copy** in the app's Settings view)
3. **Width** `1920`, **Height** `1080`.
4. OK.

That one source shows everything you switched on in Features. One source, done, no fiddling.

> **Coming from an older version?** The separate chat and music sources are gone. If you still have `http://localhost:8787/chat/` or `http://localhost:8787/music/` in OBS, delete them and use the one address above instead.

The app must be running while you stream. Without it, the browser source stays empty. Because you're sending OBS out as your virtual webcam (see [Part 1](#b-turn-obs-into-your-webcam)), the widgets now show up on the site too.

---

## 6. Tip actions (optional)

![The Dare Wheel spinning on stream after a viewer's tip](images/dare-wheel-beta.jpg)

My favourite part. Your viewers tip for an item on your tip menu, and something happens on your stream. There are two of them, the **Dare Wheel** and the **Dice Duel**, plus a **Teaser** that advertises them. All three live in one card in the **Features** view, the **Tip actions** card, each with its own tab, its own switch and its own **Save**.

How the trigger works (same for both): you add an item to your **tip menu** on the chat site, and type the **same text** as the **Trigger** in the app. Upper and lower case don't matter, but the words must match exactly. The Dare Wheel and the Dice Duel each need their **own** item, the app won't let you use the same one twice.

### The Dare Wheel

Yes, the site has its own dare game. Mine is just better, sorry not sorry:

- **Your price, your rules.** You set the token price for a spin. The site's version is always 10 tokens.
- **You're the star.** Your avatar is the dial, your six dares orbit you, and both your avatars (yours and the tipper's) watch where the beam lands.
- **It's a damn spinning wheel.** In neon. With confetti. Need I say more? 😎

1. **On the chat site:** add an item to your **tip menu**, e.g. `Spin my Dare Wheel`, with any token price you like.
2. **In the app** (Features → Tip actions → **Dare Wheel** tab): type the same text in **Trigger**.
3. Fill in **all six dares**. Yes, all six: the wheel won't spin with fewer. Then click **Save**.
4. Turn the **Dare Wheel** switch **on**.

When a viewer tips for that item, the wheel appears on your stream, a light beam circles your ring, stops on one dare, and the winning dare rises in under your avatar. Every tip menu request also updates "Latest Tip".

### The Dice Duel

You against your viewer. Fair and square, the app rolls the dice (so every OBS source shows the same match, no cheating, I checked with my lawyer).

1. **On the chat site:** add another tip menu item, e.g. `Play Dice Duel against me`.
2. **In the app** (Features → Tip actions → **Dice Duel** tab): type the same text in **Trigger**, and in **Your action if the tipper wins** what they get when they beat you. Then **Save** and turn the switch **on**.

The rules: two dice each, the higher sum wins the round, ties are rolled again, first to 3 wins. If the viewer wins, they get your action (shown like a Dare Wheel result). If you win, they get a "Good luck next time". Better luck next tip, babe.

### The Teaser

A little side pill with your avatar, above "Latest Tip", that tells your viewers what's on your tip menu: "Spin my Dare Wheel", "Play Dice Duel against me" (one line for each tip action that's on) and "See all my rewards" on your profile.

In the **Teaser** tab, switch it on and choose **always** (on screen the whole time) or **every** 1–60 minutes. Each line shows for 8 seconds. The tab has a **live preview** of the teaser exactly as it looks on stream. With no tip action switched on, the teaser has nothing to say and stays away.

---

## 7. Be right back (optional)

Phone rings, pizza's here, cat's on the keyboard. Life happens. One click and your stream gets a full-screen away screen: your avatar, a "Be right back" banner and the song that's playing, with its cover in the background.

- **Switch it on** in the **extension popup** (easiest, right next to the chat) or in the app (Features → **Be right back**). While it's on, the extension icon shows a **BRB** badge, so you don't forget you're "away". Been there.
- **Nothing gets lost.** Tips and Dare Wheel spins that come in meanwhile wait, and play one after another when you're back. Everything else keeps playing under the away screen.
- **Live chat on the away screen:** turn on **Room chat → On Be right back** and the away screen becomes a live chat: the newest message big, its sender's avatar beside it, the name in huge outlined letters, the words lighting up as if read aloud, earlier messages on the right and the last senders in a row below. Each message gets read to the end before the next one comes in; when the chat gets busy, the ones that would have to wait go straight to the list. Your viewers keep talking to each other while you're gone. Like a party in your living room while you're in the kitchen.

## 8. Room chat on stream (optional)

Turn on **Room chat → On stream** in the Features view and you get a chat box above "Latest Tip": each message with the sender's small avatar and name, new ones sliding in from below, the site's emojis included. The teaser moves up to make room.

It's **off** until you turn it on, because it shows your viewers' names and messages on your stream. Private messages never appear, they don't go through the room chat. My lawyer insisted I put that in bold. Well, he got the sentence.

---

## Updates

I keep improving things, so check back now and then. When a new version is out, the app's settings window and the extension popup show **"Update available"**. Always update **both** the app and the extension, they like to be on the same version. Then:

- **App:** download the new `.dmg` / `-setup.exe` from the [latest release](https://github.com/neongreycodes/neon-noir-stream-widgets/releases/latest) and install it over the old one. Your settings stay.
- **Extension:** unzip the new extension and replace the **contents** of your extension folder with it. Then open `chrome://extensions` and click the **reload** arrow on the extension.

---

## Troubleshooting

Something's off? Don't worry, most hiccups are quick to fix.

| Problem | What to do |
| --- | --- |
| The extension popup says **App not running** | Start the app (Applications / Start menu). |
| The popup says **Not paired** | Enter the pairing code from the app's settings window again. |
| Ratings and tips appear, but **slots / dice don't** | Check the **chat username** in the app: it must match your name on the chat site. |
| The **Dare Wheel doesn't spin** on a tip | Is the Dare Wheel switch **on**, and are **all six dares** filled in and saved? Does the **Trigger** match your tip menu item word for word? If the setup isn't complete, the card in the app warns you and a dot shows on the Features tab. Still nothing: **Show log**, it says why. |
| The **Dice Duel doesn't start** | Is its switch **on**, is a trigger *and* your action filled in and saved, and is the trigger a different item than the Dare Wheel's? |
| The **room chat** doesn't show | It's off by default: turn on **Room chat → On stream** (or **On Be right back**) in the Features view. Private messages never show, that's on purpose. |
| Something I switched off still shows / something's missing | Check its switch in the Features view: a card with a pink border is on. |
| The browser source in OBS is **empty** | Is the app running? Is the URL exactly `http://localhost:8787/neonnoirwidgets/` (the old `/chat/` and `/music/` addresses are gone)? Right-click the source → **Refresh**. |
| **Mac:** no music card | Music must be playing in the **Music** app. If you clicked "Don't Allow" before: System Settings → Privacy & Security → Automation → Neon Noir Stream Widgets → turn on **Music**. |
| The site doesn't offer **OBS Virtual Camera** | Click **Start Virtual Camera** in OBS first, then reload the chat site's page. **Mac:** check that the OBS camera extension is allowed in System Settings. |
| Viewers **don't hear the music** (Mac) | Is **Background Music** picked as the microphone on the site? In System Settings → Sound, is the output the **Multi-Output Device** and the input **Background Music**? Is the extension running? |
| Something else | In the app's settings window, click **Show log** and send me the `app.log` file (DM, Fan Mail or a GitHub issue). |

---

Music overlay based on [apple-music-obs-overlay](https://github.com/m-shintaro/apple-music-obs-overlay) by Shintaro Matsumoto (MIT). App, extension and overlays use the Inter Display font (SIL OFL 1.1) and Font Awesome 4.7 (SIL OFL 1.1 / MIT); the overlays also use canvas-confetti (ISC).

Made with love (and too much neon) by Neon Grey. 💜
