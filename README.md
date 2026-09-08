Orrery: An Interactive Model of the Solar System

Most space visualizations show you a picture of the planets. Orrery runs them: every world moving at its true relative orbital speed, live, while you fly through it.

Live demo: https://devanshi208.github.io/Orrery/

GitHub: https://github.com/Devanshi208

The core principle: The timing is real. The scale is honestly compressed, and the README says so.

What it does:

Orrery is a real-time 3D model of the solar system built entirely in the browser. It opens parked close to Earth: turning on its axis, Moon swinging around it, stars drifting behind, and entering the system pulls the camera back into the full solar view in one continuous move. No page load, no cut.

Every planet runs on its actual orbital period and actual day length:

🟡 The Sun: glow-shaded, 99.86% of the system's mass

🔵 Eight planets: real revolution and rotation timing, including Venus and Uranus spinning backwards

🌙 Moons: representative satellites orbiting each planet

💍 Saturn's rings: generated in code, Cassini division included

✨ Layered starfield: three parallax depths plus a faint galactic band

Key features

🪐 True orbital timing: Mercury laps the Sun in 88 days, Neptune takes 164.8 years, and you can watch the difference happen.

⏱️ Time control:  run the simulation from 0.15 days/sec up to roughly 2.5 years/sec.

📊 Click-to-read records: real NASA/JPL figures: diameter, gravity, day length, temperature range, composition bar, moon counts.

🛰️ Upcoming missions: BepiColombo reaching Mercury orbit, Europa Clipper arriving 2030, Dragonfly launching for Titan in 2028.

🌍 Habitability assessment: based on actual conditions, not vibes.

🎥 Free camera: drag to orbit, scroll or pinch to zoom, click a planet to fly to it, pull back for the whole system.

🏷️ Toggleable orbit paths and labels.

Tech stack

Rendering: Three.js r128 (WebGL)

Language: Vanilla JavaScript- no framework, no build step, no bundler

Textures: HTML Canvas 2D, generated procedurally at runtime

Data: NASA Planetary Fact Sheets, JPL Solar System Dynamics

Deploy: Static single file, GitHub Pages

How it works:

canvas 2D noise generation → CanvasTexture → mapped onto SphereGeometry → parent pivot group rotated per frame by (elapsedDays / orbitalPeriod) → camera rig lerps toward target in spherical coordinates → raycaster converts a click into a planet hit → data panel renders from the PLANETS array

Architecture principle: No 3D models, no image files, no external assets. Every planet surface is banded turbulence for gas giants, crater scatter for rocky worlds, continents and cloud bands for Earth is drawn in code at runtime. The entire project is one HTML file with a single CDN dependency, so it loads instantly and deploys anywhere static.

On scale:

At true scale, Neptune sits 30× further out than Earth and every planet is a sub-pixel speck in an empty field, accurate and completely unusable. Distances and radii are compressed on separate power curves that preserve relative ordering: Jupiter still dwarfs Earth, Earth still dwarfs Mercury. Orbits are drawn circular and coplanar. Moons are representative rather than complete- Jupiter really has 95.
