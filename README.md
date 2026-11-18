# Poker Clock — Android-installable PWA

A simple poker countdown timer with:
- Minutes and seconds input
- Start, pause, resume and reset
- Quick presets (5, 10, 15, 20, 30, 60 minutes)
- End-of-timer sound alert
- Offline support after the first successful load
- Best-effort screen wake lock while running

## Try it locally

A Progressive Web App must be served over HTTPS (or localhost); opening `index.html` directly as a file will not enable installation or offline caching.

For a quick local test, run a static server from this folder, for example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` in a browser on that computer.

## Install on Android

1. Upload the contents of this folder to an HTTPS static host (for example GitHub Pages, Netlify, or Cloudflare Pages).
2. Open the hosted site in Chrome on Android.
3. Wait for the page to load once while online.
4. Open Chrome's ⋮ menu and choose **Install app** or **Add to Home screen**.
5. Launch **Poker Clock** from the new home-screen icon.

## Notes

- The timer uses an absolute end timestamp, so it catches up accurately if the browser is backgrounded.
- Android may still restrict background execution or screen wake behavior depending on device settings. Keep the app open for the most reliable use.
- The sound is generated locally by the browser; no audio file or network request is needed.
- To publish updates, change `CACHE_NAME` in `sw.js` (for example `poker-clock-v2`) so installed copies refresh their cached files.
