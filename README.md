# Raspberry-Pi-Web-Showcase
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Made with Three.js](https://img.shields.io/badge/Made%20with-Three.js-000000.svg?logo=three.js&logoColor=white)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-2.0-990000.svg?logo=webgl&logoColor=white)](https://get.webgl.org/)
[![GitHub stars](https://img.shields.io/github/stars/butaraul/Raspberry-Pi-Web-Showcase.svg?style=social)](https://github.com/butaraul/Raspberry-Pi-Web-Showcase/stargazers)

A millimeter-accurate, interactive 3D WebGL visualization of the Raspberry Pi 4 Model B PCB. Built with Three.js, this single-file application lets you orbit, zoom, and inspect every component on the board with real-time tooltips and a detail panel.

text
type Board {
  dimensions: 85 × 56 × 1.2mm
  processor: Broadcom BCM2711 (quad-core Cortex-A72 @ 1.5GHz)
  memory: LPDDR4-3200 SDRAM (2GB/4GB/8GB)
  networking: Gigabit Ethernet + 802.11ac Wi-Fi + Bluetooth 5.0
  usb: 2× USB 3.0 + 2× USB 2.0
  gpio: 40-pin header (27 usable pins)
}
# Quick start

Open index.html in your browser:

# Using Python 3
python -m http.server 8000

# Using Node.js
npx serve

# Using VS Code Live Server
# Right-click index.html → Open with Live Server
Navigate to http://localhost:8000 and start exploring the board in 3D.


# Drag to orbit, scroll to zoom, click any component
Features

3D Exploration: drag to orbit the board, scroll to zoom in/out
Component Inspection: hover for tooltips, click for detailed specs in the side panel
Real-world Scale: 1 unit = 1mm, matching the actual board dimensions
Color-coded Categories: components grouped by function (CPU, networking, I/O, video, expansion, storage, power)
Legend Strip: quick reference for component categories
Detail Panel: shows component name, category, and technical specifications
Responsive Design: works seamlessly on desktop and mobile devices
Modern Dark Theme: custom dark UI with glass-morphism effects
Single-file Distribution: everything (HTML, CSS, JS, 3D model) in one file
Project Structure


raspberry-pi-4-viewer/
├── index.html              # Single-file application
│                           # - HTML structure
│                           # - CSS styles (dark theme, glass-morphism)
│                           # - Three.js scene setup
│                           # - Interactive controls (orbit/zoom/click)
│                           # - Component registry with specs
│                           # - Base64-embedded glTF model
├── README.md               # This file
└── LICENSE                 # MIT License
Component Registry

The viewer includes detailed information for 30+ components on the board:

Category	Components	Color
Core	CPU, RAM, Broadcom SoC	Red (#d1445f)
Networking	Ethernet port, Wi-Fi/Bluetooth	Green (#3fa46f)
I/O	USB 3.0, USB 2.0, Audio jack	Blue (#4f8fd6)
Video	Micro HDMI ports, MIPI DSI	Purple (#9573d1)
Storage	microSD slot	Teal (#3fb6ac)
Power	USB-C, PoE header	Gold (#d4a94f)
Expansion	40-pin GPIO header, MIPI CSI-2	Orange (#d98a3d)
Technology Stack

Three.js - 3D rendering engine (r160)
GLTFLoader - Loading and parsing the 3D model
WebGL 2.0 - Hardware-accelerated rendering
CSS Custom Properties - Theming and dark mode
ES Modules - Modern JavaScript with import maps
Commands

Command	Description
python -m http.server 8000	Start a local server (Python 3)
npx serve	Start a local server (Node.js)
open index.html	Open directly in browser (some features may be limited)
Usage Guide

Controls

Drag (mouse/touch) → Orbit around the board
Scroll (mouse/pinch) → Zoom in/out
Click (mouse/tap) → Select a component → Detail panel updates
Hover (mouse) → Component name tooltip appears
Interactive Elements

Detail Panel (right side): displays selected component's name, category, and specifications
Legend Strip (bottom): shows all component categories with their colors
Explore Button (top-right): auto-rotates the board for a guided tour
Zoom Readout (bottom-left): shows current zoom level
Design Notes

3D Model: the board geometry is embedded as a base64-encoded glTF asset, originally converted from a SketchUp assembly. 1 Three.js unit equals 1 millimeter.
Lighting: a 3-point lighting system (warm key, cool rim, ambient fill) plus hemisphere light ensures metallic components render correctly without a full environment map.
Performance: pixel ratio is capped at 2× to balance quality and performance; particle background is drawn once and cached.
Error Handling: the model loads with a fallback veil; if loading fails, the user sees a loading indicator rather than a blank canvas.
Accessibility: the canvas includes ARIA labels for screen readers; keyboard controls are supported (arrow keys, plus/minus).
Tests

# No automated tests currently - manual testing recommended
# Test on different browsers:
# - Chrome (recommended)
# - Firefox
# - Safari
# - Mobile browsers

