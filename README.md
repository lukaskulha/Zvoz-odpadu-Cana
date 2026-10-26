# Waste Collection Calendar – Čaňa 2026

A free, lightweight web app (PWA) with the 2026 waste collection calendar for the village of **Čaňa, Slovakia**.

**Live app:** https://zvoz-odpadu-cana-kosit.netlify.app/

> This is an unofficial, community project. It is not affiliated with the municipality of Čaňa or KOSIT a.s. The dates were transcribed from the official KOSIT collection calendar for Čaňa 2026: https://www.kosit.sk/wp-content/uploads/2025/12/Cana.pdf. If in doubt, the official calendar applies. Found a mistake? Please open an issue.

## Features

- Days remaining until the next collection of mixed waste, glass, paper, and plastics/metals/beverage cartons
- Warnings on the tiles: red "take it out" notice for collections today or tomorrow, yellow notice for collections later this calendar week
- Colour-coded monthly calendar with today highlighted
- Choose whether mixed waste is collected on **Thursday or Friday**, depending on your street (the days remaining update instantly)
- "Add to calendar" button: generates an `.ics` file you can import into iPhone, Android or any other calendar app. You choose which waste types to include and when to be reminded:
  - day before: 7:00, 13:00 or 19:00
  - on collection day: 6:00, 7:00 or 10:00
- A guide to what belongs in each bin and what does not
- Light and dark theme: automatic (follows your phone) or chosen manually
- Installable as an app on your home screen, works offline
- Interface in Slovak

## Install on your phone

- **iPhone:** open the link in Safari, tap Share, then **Add to Home Screen**.
- **Android:** open the link in Chrome, tap the ⋮ menu, then **Install app** or **Add to Home screen**.

## Privacy

The app stores your settings (collection day, theme, reminder times) only in your own browser using `localStorage`. There are no accounts, no cookies, and no server-side data.

Visit counts are measured anonymously with [GoatCounter](https://www.goatcounter.com/), which uses no cookies and collects no personal data. **If you fork this project, replace the GoatCounter script tag at the bottom of `index.html` with your own, or remove it.** Otherwise your visits will be counted in the original author's statistics.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app: markup, styles and JavaScript in one file |
| `sw.js` | Service worker for offline use |
| `manifest.webmanifest` | Web app manifest (name, icons, colours) |
| `icon-192.png`, `icon-512.png` | App icons |

There is no build step and there are no dependencies.

## Run locally

Download the files and serve the folder with any static web server, for example:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. The service worker and install prompt need `localhost` or HTTPS, so opening `index.html` directly from disk will not enable them.

## Deploy

Any static host works (Netlify, GitHub Pages, Cloudflare Pages). On Netlify you can drag and drop the folder, or link this repository so every commit deploys automatically.

## Updating the dates

Collection dates are defined in the `D` object at the top of the main script in `index.html`. Keys are `K` (mixed waste), `S` (glass), `P` (paper) and `L` (plastics and metals), each mapping month numbers to lists of days. The Friday option for mixed waste is derived by shifting the Thursday dates by one day. When KOSIT publishes the next year's calendar, update these lists and the year in the page title and calendar.

## Contributing

Corrections and ideas are welcome through issues and pull requests.

## License

Released under the MIT License, see [LICENSE](LICENSE). The collection schedule itself comes from KOSIT a.s.
