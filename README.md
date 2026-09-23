# Asia 2026 — An Interactive 3D Travel Atlas

**21 days · 16 cities · 6 flags · ≈29,950 km** — from Kuala Lumpur to Shanghai, 12 October – 2 November 2026.

**[Open the live atlas →](https://ardaseyhan34.github.io/asya2026/)**

---

## Why I built this

I'm about to set off on a 21-day journey across Southeast and East Asia. Instead of keeping the plan in a long PDF itinerary, I wanted a way to **really get to know the route before I go**, and to **share it with friends and family in a format they can explore themselves**.

So I turned my master itinerary into an interactive 3D atlas, built with the help of AI. I set the goals, the route and the content, and reviewed every iteration. The AI assistant (Claude by Anthropic) helped with research, code and visual design.

## What you can do

- **Explore a 3D globe.** Real Earth imagery with terrain relief, clouds, atmosphere and city lights on the night side, all rendered in WebGL.
- **Walk through the trip day by day.** Each of the 21 days has an hour-by-hour plan, must-dos, food to try, critical notes and a photo spot. The day's stops appear as numbered pins on the map.
- **Fly into every city.** The camera tilts down into 3D city views with procedural buildings, real rail lines, highways, rivers and coastlines. Stylized landmarks include the Petronas Towers, Canton Tower, Tianmen Mountain, the Great Wall and the Temple of Heaven.
- **Follow the journey.** Flights arc through the sky, and trains, buses and the ferry glow along the ground with animated 3D vehicles.
- **See the logistics at a glance.**
  - Ticket wall: every flight and train, with its status and Plan B.
  - Prep timeline: booking deadlines calculated from today's date.
  - Red lines: Plan A / Plan B for the riskiest connections.
  - Survival kit: payments, internet, trains, luggage and safety tips per country.
- **Watch the 30-second film.** A cinematic flythrough of the whole route, with a live distance counter and flags collected along the way.
- **Use it on the road.** The site works on mobile, and you can tick off each day's activities; progress is saved in your browser.

## The route

| Chapter | Days | Stops |
|---|---|---|
| Malaysia & Singapore | 1–3 | Kuala Lumpur · Melaka · Singapore |
| Philippines | 4–5 | Manila |
| Macau & Hong Kong | 6–7 | Macau · Hong Kong |
| Pearl River Delta | 8–9 | Guangzhou (Canton Fair) · Shenzhen |
| Hunan | 10–11 | Zhangjiajie · Furong · Tianmen · Fenghuang |
| Heart of China | 12–16 | Chongqing · Chengdu · Xi'an |
| Beijing & Shanghai | 17–21 | Beijing · Great Wall (Mutianyu) · Shanghai |

**Getting around:** 4 flights · 11 train rides (2 overnight) · 2 intercity buses · 1 ferry

## How it's built

A single static page with no build step, hosted on GitHub Pages.

- **3D rendering:** [three.js](https://threejs.org/) (WebGL). Custom shaders for the Earth, atmosphere and screen-space route lines; procedural models for landmarks and vehicles; instanced meshes for city buildings.
- **Map layers:** [D3](https://d3js.org/) and [TopoJSON](https://github.com/topojson/topojson), used to generate border, coastline and city-detail textures on the fly.
- **Interface:** vanilla JavaScript and CSS.
- **Content:** a researched master itinerary, turned into structured data for all 21 days.

| File | Purpose |
|---|---|
| `index.html` | The whole app: UI, 3D engine and itinerary data |
| `day.jpg`, `night.jpg` | Earth day and night textures |
| `mask.jpg` | Land/water mask and cloud layer |
| `elev_g.png`, `elev_a.png` | Global and Asia elevation used for terrain relief |
| `detail.json` | Coastlines, urban areas, railways, highways, rivers and lakes for Asia |

## Controls

| Action | Desktop | Mobile |
|---|---|---|
| Pan the map | Drag | One-finger drag |
| Rotate / tilt | Right-drag or Shift + drag | Two-finger twist |
| Zoom | Scroll wheel | Pinch |
| Previous / next day | ← / → | Day strip or arrows in the panel |
| Close panel / exit film | Esc | × button |

## Credits

- Earth textures: [three.js examples](https://github.com/mrdoob/three.js/tree/dev/examples/textures/planets), derived from NASA Blue Marble and Black Marble imagery
- Geographic data: [Natural Earth](https://www.naturalearthdata.com/) (public domain) and [world-atlas](https://github.com/topojson/world-atlas)
- Fonts: Big Shoulders Display, Manrope and IBM Plex Mono via Google Fonts
- Libraries: three.js (MIT), D3 (ISC), TopoJSON (ISC)

## Notes

- Train numbers and timings are targets; they get re-checked when ticket sales open.
- Map pins for sights are approximate, and ground distances are estimates.
- City buildings are generated procedurally. Landmark models are stylized and drawn larger than life so they stay visible.

---

Built by **Arda Seyhan** with AI assistance, as a personal project to plan, visualize and share a once-in-a-lifetime trip.
