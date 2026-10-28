# Haze Watch

A single-page dashboard for Singapore haze and ASEAN weather.

- **Haze (Singapore only):** 24-hour PSI, PM2.5 and PM10 by area from the National Environment Agency, via the data.gov.sg real-time APIs (`/v2/real-time/api/psi` and `/v2/real-time/api/pm25`).
- **Weather (16 ASEAN cities):** current conditions from the Open-Meteo forecast API.

The page fetches both sources in the browser when it opens, every 15 minutes while it is visible, and on **Refresh live data**. If a source can't be reached, it keeps showing the last data it has (a built-in snapshot on first load) and says which source failed.

## Deploy on Vercel

It's a static site with no build step.

1. Import this repository in Vercel.
2. Framework preset: **Other**. Leave the build command and output directory empty.
3. Deploy.

`vercel.json` sets clean URLs, no-cache headers so viewers always get the latest page, and a Content Security Policy that only allows the two data APIs and Google Fonts.

## Run locally

Open `index.html` in a browser, or serve the folder:

```
npx serve .
```
