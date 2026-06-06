# Space Dodge — Dev Log

Live: https://play-space-dodge.netlify.app  
Repo: https://github.com/jcleineai/space-dodge

---

## COMPLETED TODAY (2026-05-31)

- Realistic space background with parallax stars, nebula clouds, and a scrolling planet with rings and craters
- Rocky asteroid redesign — radial gradient shading, surface cracks, craters, highlight spot
- Better ship design — cockpit canopy, engine nacelles, hull panel lines, thruster flame gradient
- Bigger explosions — flash burst, fireball particles, debris chunks, rising smoke
- Diagonal turret bullets (vx: -3, vy: ±4) — fire from cave wall turrets toward players
- Cave walls slide in smoothly from top and bottom when score passes 256
- Debug mode added (toggle with D key) then removed from production build
- Netlify deployment fixed — was deploying wrong project folder, now deploys from correct space-dodge dir

---

## KNOWN BUGS

- **Turret bullets go diagonal after boss defeated** — comment in code says vx should be 0 (pure vertical), but code has vx: -3; post-boss score spike shifts the visual mismatch. Fix: set vx: 0 on bullet spawn.
- **Netlify needs redeploying after each change** — no CI/CD hooked up, manual `netlify deploy --prod --dir .` required

---

## UP NEXT

- Online co-op with PeerJS (P1 hosts, P2 joins via 4-digit room code)
- Fix post-boss bullet direction bug (vx: -3 → vx: 0)
- Named high score table
