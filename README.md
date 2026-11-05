# Room 214: 3D Classroom

An interactive 3D render of an under-resourced public-school classroom, built with [Three.js](https://threejs.org/). It is the empty-room setting for a five-minute interactive story about what it's like to teach in an understaffed school.

You can drag to look around the room, scroll or pinch to zoom, and press **Auto-orbit** for a slow tour.

## What's in the room

- 16 student desks with chairs, papers and books
- A chalkboard reading "Homeroom 10A", with the day's work, a math problem and a sub-coverage note
- A teacher's desk with stacked papers, a laptop and a coffee mug
- Windows letting in warm late-afternoon light, a radiator, a bulletin board, posters, a bookshelf and a door
- Signs of underfunding: water-stained walls, a stained ceiling tile, a missing ceiling tile and a flickering fluorescent light

## Run it

The project is a single file with no build step or installs.

- **Locally:** open `index.html` in any modern browser. You need an internet connection, because Three.js and the fonts load from public CDNs.
- **GitHub Pages:** go to **Settings → Pages**, set the source to **Deploy from a branch**, then pick `main` and `/ (root)`. The site goes live at `https://<username>.github.io/<repo>/`.

## Controls

| Action | Mouse / trackpad | Touch |
|---|---|---|
| Look around | Click and drag | Drag |
| Zoom | Scroll | Pinch |
| Slow tour | Auto-orbit button | Auto-orbit button |

## Customizing

All of the code is in the `<script>` section of `index.html`.

| To change | Look for |
|---|---|
| Room size | `const W=16,D=20,H=5` (width, depth, height) |
| Wall, floor and ceiling look | `wallTex`, `floorTex`, `ceilTex` |
| Chalkboard text | `boardTex`, plus the redraw inside `document.fonts.load(...)` (edit both) |
| Window sunlight | `sun` |
| Ceiling lights | `panels`; the flickering one is `panels[3]` |
| Desk layout | `[-4.8,-1.6,1.6,4.8].forEach(x=>[-3.2,-.2,2.8,5.8]...` (x = columns, z = rows) |
| Starting camera view | `theta`, `phi`, `radius` |

Students are left out by the `return;` inside `makeStudent()`. Delete that line to bring the antenna students back. They will sit at their desks without animation.

## Built with

- [Three.js r128](https://cdnjs.com/libraries/three.js), loaded from cdnjs
- Google Fonts: Patrick Hand and Nunito
- Textures drawn in code with the Canvas API, so the project has no image files
