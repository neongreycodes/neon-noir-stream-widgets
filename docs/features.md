# Features

Everything that can light up on your stream, and how to set it up. Everything here is optional: switch on what you like, leave off what you don't.

## The Features view

In the app's **Features** view, every part of the overlay has its own switch: tip and rating banners and cards, Dice Roll and Slot Spins, the music player (on stream and on Be right back), the tip actions, the teaser and the room chat. Switch something off and OBS follows at once, and the cards at the bottom left close the gap. A card with a **pink border** is on.

## Themes

**Neon Noir Dark** (the default, neon at night) and **Neon Noir Light** (the same street by day). Pick one in the app's **Settings** view, and OBS follows within 2 seconds. Behind the banners, cards and games there's a slowly scrolling neon grid, very 80s, and way lighter on OBS than the old GIF backgrounds ever were.

**Tip:** add `?theme=light` or `?theme=dark` to the OBS browser source URL to fix its look, whatever the app is set to.

---

## Tip actions

![The Dare Wheel spinning on stream after a viewer's tip](../images/dare-wheel-beta.jpg)

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

## Be right back

Phone rings, pizza's here, cat's on the keyboard. Life happens. One click and your stream gets a full-screen away screen: your avatar, a "Be right back" banner and the song that's playing, with its cover in the background.

- **Switch it on** in the **extension popup** (easiest, right next to the chat) or in the app (Features → **Be right back**). While it's on, the extension icon shows a **BRB** badge, so you don't forget you're "away". Been there.
- **Nothing gets lost.** Tips and Dare Wheel spins that come in meanwhile wait, and play one after another when you're back. Everything else keeps playing under the away screen.
- **Live chat on the away screen:** turn on **Room chat → On Be right back** and the away screen becomes a live chat: the newest message big, its sender's avatar beside it, the name in huge outlined letters, the words lighting up as if read aloud, earlier messages on the right and the last senders in a row below. Each message gets read to the end before the next one comes in; when the chat gets busy, the ones that would have to wait go straight to the list. Your viewers keep talking to each other while you're gone. Like a party in your living room while you're in the kitchen.

## Room chat on stream

Turn on **Room chat → On stream** in the Features view and you get a chat box above "Latest Tip": each message with the sender's small avatar and name, new ones sliding in from below, the site's emojis included. The teaser moves up to make room.

It's **off** until you turn it on, because it shows your viewers' names and messages on your stream. Private messages never appear, they don't go through the room chat. My lawyer insisted I put that in bold. Well, he got the sentence.

---

[← Back to the start](../README.md) · [← Install the widgets](install.md) · [Next: Troubleshooting →](troubleshooting.md)
