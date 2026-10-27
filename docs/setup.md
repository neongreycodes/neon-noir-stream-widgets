# The basic setup

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

Now whatever OBS shows is what your viewers see, widgets included once you've added them (see [Install the widgets](install.md#5-add-it-to-obs)). OBS has to stay open with the virtual camera running while you stream.

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

[← Back to the start](../README.md) · [Next: Install the widgets →](install.md)
