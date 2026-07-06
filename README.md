# For Michelle 🏮 — birthday gift site

A single-file mobile web experience: countdown → lantern dedications → "HAPPY BIRTHDAY POTATO" sky reveal → candle wishes → blow-out via microphone → letter → photo gallery.

## What's in here

```
for-michelle/
├── index.html    ← the entire experience (edit the CONFIG block at the top of the <script>)
├── photos/       ← drop her photos here (1.jpg, 2.jpg, 3.jpg, 4.jpg ...)
├── assets/       ← optional: music.mp3 (background song) and voice.mp3 (your voice note)
└── README.md
```

## ✏️ What YOU must edit before July 8 (all inside index.html, in the CONFIG block)

1. **`wishes`** — currently my sample drafts. Make them yours.
2. **`letter`** — three placeholder paragraphs marked "EDIT ME". Write the real letter.
3. **`signature`** — replace "YOUR NAME HERE".
4. **`gallery`** captions — one line per photo.
5. **`fireflyMessage`** — optional, but a good slot for an inside joke.
6. The **`dedications`** are already your words — reorder or tweak freely. Add/remove `photo:` on any of them.

Anything you don't want: photo lanterns fall back to text if the file is missing, gallery skips missing images, and the music/voice buttons hide themselves if the mp3s aren't there. Nothing breaks by leaving something out.

## Photos

- Save as `photos/1.jpg`, `photos/2.jpg`, etc. (names must match what's in CONFIG).
- Compress them first at https://squoosh.app — aim under ~300 KB each so nothing lags on mobile data in Manila.
- Portrait orientation looks best.

## Music / voice note (optional)

- Background song → `assets/music.mp3`. A soft instrumental works better than a vocal track behind reading.
- Your voice note → `assets/voice.mp3` (record on your phone, convert to mp3 if needed).
- Playing the voice note auto-pauses the music.

## Test it locally

```
cd for-michelle
npx serve
```
Open the printed localhost URL **on your phone won't work directly** — easiest is to test in your computer browser with mobile view (F12 → device toolbar), or just deploy to Vercel and test the live URL on your phone.

**Skip the countdown while testing:** add `?test=1` to the URL, e.g. `http://localhost:3000?test=1`.
The mic blow-out needs HTTPS or localhost — it will work on localhost and on Vercel, and the press-and-hold fallback always appears a few seconds later regardless.

## Deploy to Vercel

Easiest way (no git needed):
1. Go to https://vercel.com/new
2. Drag the whole `for-michelle` folder onto the page (or use "Deploy without Git").
3. Give the project an unguessable name, e.g. `mkwy-0708-lanterns` — the URL becomes `mkwy-0708-lanterns.vercel.app`. Since her photos are on it, don't use her full name in the URL.

Or the way you already know from Virtual Fit: push the folder to a GitHub repo and import it in Vercel. Every `git push` redeploys.

The page already has a `noindex` tag so search engines won't list it.

## The QR code

1. Deploy first, confirm the live URL works on YOUR phone end to end (use `?test=1`, and test the real mic blow-out).
2. Generate a QR at any generator (e.g. qr-code-generator.com) pointing to the URL **without** `?test=1`.
3. Print it, put it in the sealed envelope with your handwritten note, hand it to her July 7. Tell her: *do not open until midnight.*

## Timeline check

- The countdown unlocks at **midnight July 8, 2026, Philippine time** (set in `targetDate`).
- If she opens the QR before midnight she sees only the countdown and one distant floating lantern. That's intentional.

## The flow, for reference

Countdown gate → tap **Begin** → tap anywhere to release each of the 7 lanterns (message card auto-appears as each rises; lanterns collect in the sky) → firefly drifts by occasionally (tapping it = bonus message) → after the 7th, "Tap once more…" → the lanterns form **HAPPY BIRTHDAY POTATO** → fade to the cake → tap each flame for a wish → last wish prompts the blow-out → she blows into the mic (or holds the fallback button) → candles die one by one → dark → single candle → your letter → voice note → photo gallery → "See you when you're home."
