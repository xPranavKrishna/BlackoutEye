# 👀 Eye Blackout — The Most Useless App Ever Built (Entirely on a Phone)

A "screensaver" that watches your eyes and refuses to let you look at your own screen. Open your eyes → black screen. Close your eyes → it shows you a laughing face roasting you. That's it. That's the whole app.

## The Story

Built during a volunteering shift at **Calicut Tinkerspace**, while a "useless projects" hackathon was going on right next to me — except I wasn't even entered in it. No laptop. Just a phone, the GitHub mobile site, CodePen, and Claude talking me through the code line by line.

No IDE. No `npm install`. No build step. Just copy-paste, save, refresh, repeat — until a face mesh model running off a CDN started reading my eyelids in real time and roasting me for it.

If that doesn't count as "useless engineering," nothing does.

This was actually **build #2 of the day** — build #1 was [Useless Lens](https://github.com/xPranavKrishna/useless-lens), made the same phone-only, no-laptop way.

## What It Actually Does

- Uses your **front camera** + Google's MediaPipe FaceMesh (loaded straight from a CDN, no install needed) to track your face in real time
- Calculates the **Eye Aspect Ratio (EAR)** — a simple geometry trick using eye landmark points — to figure out if your eyes are open or closed
- **Eyes open** → full black screen, because apparently you don't deserve to see your phone if you're going to look at it
- **Eyes closed** → a sticker-style card pops up with a bouncing laughing face, a speech bubble roasting you (you'll have to try it to see what it says), and a little row of clowns, because closing your eyes is somehow the "reward" state

## Tech Stack

- Plain HTML, CSS, and vanilla JS — no framework, no bundler
- [MediaPipe FaceMesh](https://github.com/google/mediapipe) for face landmark detection, loaded via jsDelivr CDN
- Hosted for free on **GitHub Pages**

## Running It Yourself

1. Grab `index.html` from this repo
2. Host it anywhere over **HTTPS** (GitHub Pages, CodePen full-page view, Netlify, whatever) — camera access needs a secure origin, so opening the file directly won't work
3. Open the hosted link on your phone, allow camera access
4. Stare at your phone. Get blacked out. Close your eyes. Get roasted. Repeat as needed.

Tweak the `EAR_THRESHOLD` constant near the top of the script if the eye detection feels too sensitive or not sensitive enough.

## Known Quirks

- On phone, the eye detection can flicker or misfire a bit if the camera angle or how you're holding/looking at the phone isn't quite right — it's tuned for a fairly straight-on face position, so tilting the phone too much or looking off to the side can confuse it
- Good, even lighting on your face helps a lot; low light makes the eye landmarks less reliable

## Credits

- Built by **Pranav**, on a phone, with no laptop in sight
- Code, debugging, and design help from **Claude** (Anthropic)
- Inspired by pure boredom and a hackathon I wasn't even part of

---

*If you've read this far, you now know more about a useless app than most people know about their actual job. You're welcome.*
