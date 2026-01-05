# 🗺️ 3D Terrain Maps with Leaflet

A beautiful, mobile-friendly 3D terrain map viewer powered by MapLibre GL JS and deployed automatically to GitHub Pages.

## ✨ Features

- **Full 3D Terrain Visualization** - Experience realistic terrain with elevation data
- **Mobile Optimized** - Touch-enabled controls that work perfectly on phones and tablets
- **Interactive Locations** - Quick navigation to famous landmarks:
  - Grand Canyon
  - Mt. Everest
  - Swiss Alps
  - Yosemite Valley
- **Real-time Controls** - Pinch to zoom, tilt, and rotate the map
- **Auto-deployment** - Automatic GitHub Actions deployment to GitHub Pages

## 🚀 Live Demo

Once deployed, your map will be available at:
`https://[your-username].github.io/Leaflet_3d_terrain_maps/`

## 🛠️ Technology Stack

- **Leaflet.js** - Leading open-source JavaScript library for interactive maps
- **MapLibre GL JS** - Integrated via Leaflet plugin for 3D terrain support
- **@maplibre/maplibre-gl-leaflet** - Plugin that brings 3D capabilities to Leaflet
- **OpenStreetMap** - Map tile provider
- **Terrain RGB** - Elevation data for 3D terrain
- **GitHub Actions** - Automated CI/CD pipeline
- **GitHub Pages** - Static site hosting

### Leaflet API Compatibility

This implementation uses **genuine Leaflet.js** with all standard Leaflet methods available:
- `map.flyTo()`, `map.setView()`, `map.getZoom()`, etc.
- Standard Leaflet markers with `L.marker()`
- Leaflet popups, tooltips, and controls
- All Leaflet events (click, zoom, move, etc.)
- Layer control for switching between map styles
- Full compatibility with existing Leaflet code

## 📱 Mobile Support

The map is fully optimized for mobile devices with:
- Responsive design that adapts to any screen size
- Touch-enabled controls (pinch, pan, tilt, rotate)
- Optimized performance for mobile browsers
- Geolocation support to find your current location

## 🎮 Controls

### Desktop
- **Left click + drag** - Pan the map
- **Right click + drag** - Rotate and tilt
- **Scroll** - Zoom in/out
- **Ctrl + click + drag** - Rotate

### Mobile
- **One finger drag** - Pan the map
- **Two finger pinch** - Zoom in/out
- **Two finger rotate** - Rotate the map
- **Two finger drag up/down** - Tilt the map

## 🔧 Setup & Deployment

### Prerequisites
1. A GitHub account
2. GitHub Pages enabled for your repository

### Deployment Steps

1. **Enable GitHub Pages**
   - Go to your repository settings
   - Navigate to "Pages" section
   - Under "Source", select "GitHub Actions"

2. **Push Code**
   - The workflow will automatically trigger on push to main/master/claude branches
   - Or manually trigger from the Actions tab

3. **Access Your Map**
   - Once deployed, visit: `https://[username].github.io/[repository-name]/`

## 📂 Project Structure

```
.
├── index.html              # Main map application
├── .github/
│   └── workflows/
│       └── deploy.yml      # GitHub Actions deployment workflow
└── README.md              # This file
```

## 🌍 Adding Custom Locations

To add your own favorite locations, edit the `index.html` file and add a new function:

```javascript
function flyToCustomLocation() {
    map.flyTo({
        center: [longitude, latitude],
        zoom: 12,
        pitch: 70,
        bearing: 0,
        duration: 3000,
        essential: true
    });
}
```

Then add a button in the controls section:
```html
<button class="btn" onclick="flyToCustomLocation()">My Location</button>
```

## 🎨 Customization

### Change Terrain Exaggeration
In `index.html`, modify the exaggeration value (default is 1.5):
```javascript
terrain: {
    source: 'terrain',
    exaggeration: 2.0  // Make terrain more dramatic
}
```

### Change Map Style
Replace the OpenStreetMap tiles with other providers by modifying the `raster-tiles` source.

### Adjust Initial View
Change the starting location, zoom, and pitch in the map initialization:
```javascript
center: [-111.5, 36.1],  // [longitude, latitude]
zoom: 11,
pitch: 60,
bearing: 0
```

## 📄 License

This project uses:
- MapLibre GL JS (BSD 3-Clause License)
- OpenStreetMap data (ODbL License)

## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 🙏 Credits

- Map data © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors
- Terrain data from MapLibre demo tiles
- Built with [MapLibre GL JS](https://maplibre.org/)
