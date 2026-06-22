# Speech Therapy

A mobile-first daily speech and word-retrieval practice app. It guides you through a
short daily session of exercises, lets you play any exercise on its own, tracks daily
health signals (medication, protein, sedatives, and memory/speech/anxiety ratings), and
surfaces trends, correlations, and a calendar heatmap so you can see patterns over time.
A points / level / streak system keeps the daily habit going.

> This app is a practice companion. It is meant to **complement professional speech and
> language therapy, not replace it.** It does not provide medical advice.

## Features

- **Daily session** — a 6-exercise plan that rotates through **14 agendas** (two weeks of
  distinct sound focuses, e.g. /s/–/sh/, plosives, /r/ & /l/, blends), so nothing repeats
  within 14 days. Today's weekday is selected automatically (Sun–Sat).
- **14 exercises** across Word Retrieval, Vocabulary, Diction, Sentence, and Memory —
  including Fluency Sprint, Twister Trainer, Word Upgrade, PREP, Sentence Builder, Feature
  Map, Cue Ladder, 30-Second Summary, and an optional voice-recorded Daily Speech Sample.
- **Mini-Games** — play any single exercise on demand, filtered by category.
- **Daily Log** — quick yes/no trackers plus memory, speech, and anxiety ratings and a note.
- **Progress** — plain-language insights, 14-day trend charts, correlation cards, and a
  month/quarter calendar heatmap.
- **30 levels** with a fast-early / steep-late curve, plus points and daily streaks.
- **Export / Import** — back up all your data to a JSON file or restore it on another
  device or browser (bottom of the Progress page).
- **Works offline-ish** — everything runs in the browser and saves locally; no account,
  no server, no tracking.

## Run it

It's a single static file with no build step.

- **Locally:** download the repo and open `index.html` in any modern browser
  (Chrome, Safari, Edge, Firefox).
- **On your phone:** open the hosted URL (see below), then use your browser's
  **Share → Add to Home Screen** so it opens full-screen like an app and keeps your data.

## Deploy free with GitHub Pages

1. Push this repo to GitHub (see "Upload to GitHub" below).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Select branch **main** and folder **/ (root)**, then **Save**.
5. After a minute your app is live at
   `https://<your-username>.github.io/<your-repo-name>/`.

Because the main file is named `index.html` at the repo root, Pages serves it automatically.

## Upload to GitHub

**Option A — website (no tools):**
On your repo page click **Add file → Upload files**, drag in `index.html`, `README.md`,
`LICENSE`, and `.gitignore`, then **Commit changes**.

**Option B — command line:**
```bash
cd speech-therapy-app
git init
git add .
git commit -m "Speech Therapy app"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

## Your data & backups

Your progress is saved automatically in the browser's local storage **on each device and
browser separately** — it is private to you and never leaves your device on its own.

Because it's per-device, use **Progress → Your data**:
- **Export backup** downloads a file like `speech-therapy-backup-YYYY-MM-DD.json`.
- **Import backup** restores that file on another device/browser. Importing **replaces**
  the data currently on that device, so export first if you want to keep it.

Tip: clearing your browser data, or using private/incognito mode, will erase local
progress — keep an exported backup.

## Project structure

```
speech-therapy-app/
├── index.html     # the entire app (HTML + CSS + JS in one file)
├── README.md
├── LICENSE
└── .gitignore
```

## Tech notes

- Single self-contained `index.html`. No build tools, no framework, no dependencies to
  install. State persists via `localStorage`.
- Loads the Nunito font and Font Awesome icons from CDNs; without a connection it falls
  back to system fonts and still works.
- The optional audio recording uses the browser's microphone API and degrades gracefully
  if a mic isn't available.
- Honors the OS "reduce motion" setting.

## License

MIT — see [LICENSE](LICENSE).
