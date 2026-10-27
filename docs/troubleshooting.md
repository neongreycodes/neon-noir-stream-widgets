# Troubleshooting

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

[← Back to the start](../README.md) · [← Features](features.md)
