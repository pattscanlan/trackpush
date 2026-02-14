# TrackPush — SAR Route Share

A lightweight, zero-dependency web app that lets search and rescue teams share GPS routes with anyone via a simple URL. No app install, no account, no paywall.

## How It Works

**SAR team (Create Mode):**
1. Open TrackPush and tap waypoints on the topo map, search for locations, paste coordinates, or upload a GPX file
2. Click "Generate Share Link" — the entire route is encoded into the URL
3. Send the link to the field party via SMS, satellite messenger, radio relay, or any channel

**Field party (Follow Mode):**
1. Open the link in any mobile browser
2. See the route on a topographic map with their live GPS position
3. Get real-time distance, compass bearing, and progress toward safety

## Features

- **Topographic base map** (OpenTopoMap) with trails, contours, and terrain features
- **Multiple input methods**: tap-to-place, place name search, decimal coordinates, DMS coordinates, GPX upload
- **No backend required** — the route is encoded in the URL hash using polyline compression
- **Works on any device** with a modern browser and GPS
- **HTTPS required** for Geolocation API (GitHub Pages provides this automatically)

## Deployment

This is a single `index.html` file. To deploy on GitHub Pages:

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch**, select `main`, root `/`
4. Your app will be live at `https://yourusername.github.io/trackpush/`

## Tech Stack

- [Leaflet.js](https://leafletjs.com/) for mapping
- [OpenTopoMap](https://opentopomap.org/) for topographic tiles
- [Nominatim](https://nominatim.openstreetmap.org/) for geocoding (no API key)
- Browser Geolocation API for GPS tracking
- Google Polyline Algorithm for URL-safe route encoding

## Limitations

- **Requires connectivity** to load the page and map tiles initially
- **No offline tile caching** (planned: service worker for pre-caching tiles along route corridor)
- **Nominatim usage policy**: max 1 request/second, appropriate for interactive search but not bulk geocoding

## License

MIT
