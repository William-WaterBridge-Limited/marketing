# williamwaterbridge.com

The public website for William WaterBridge Limited, served free by GitHub Pages from the `main` branch.

| Path | File |
| --- | --- |
| `/` | `index.html` |
| `/glean/privacy/` | `glean/privacy/index.html` (Glean's privacy policy, linked from Google Play) |
| Any missing page | `404.html` |

Shared styles are in `assets/site.css`. `CNAME` tells GitHub Pages to serve the site at williamwaterbridge.com.

## Background video

`assets/earth-night.mp4` is trimmed and cropped from NASA's time-lapse *City Lights over Eastern United States*
(ISS Expedition 30, April 12, 2012), from the ISS Crew Earth Observations Facility and the Earth Science and
Remote Sensing Unit, NASA Johnson Space Center ([source](https://eol.jsc.nasa.gov/Videos/CrewEarthObservationsVideos/)).
NASA imagery is generally not copyrighted; keep the credit in the footer. It was made with:

```bash
ffmpeg -ss 4 -t 30 -i eastus_iss_20120412HD_web.mp4 -an \
  -vf "crop=624:440:400:0,scale=1280:-2:flags=lanczos,fade=t=in:st=0:d=1,fade=t=out:st=29:d=1,format=yuv420p" \
  -c:v libx264 -preset slow -crf 27 -movflags +faststart earth-night.mp4
```

## Editing

Plain HTML and CSS; no build step. Preview locally with `python3 -m http.server` and open http://localhost:8000.
