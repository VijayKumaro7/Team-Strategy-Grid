# Team Strategy Grid (Hot‑Seat Strategy Prototype)

A single‑file HTML/JS tactics game with:
- Team‑specific fog of war
- Multi‑unit selection & AP movement (3 AP/unit/turn)
- 60s decision timer with auto end turn
- Procedural map generation with seed & difficulty
- In‑round chat with per‑turn comms budget
- Built‑in sanity tests (right panel)
- Optional WebSocket relay stub for mirroring chat/events (experimental)

## Quick start
Just open `index.html` in any modern browser.

### Controls
- **Click / Shift+Click / Drag box**: select units
- **Right‑click** (or **M**): move selected units toward cursor, spending AP
- **E**: end turn
- **F**: toggle fog of war
- **ESC**: clear selection
- New procedural map: set **Seed** + **Difficulty** and click **New Map**

## Built‑in tests
Open the right panel and click **Run Tests** (or **New Map + Tests**). These validate:
- Map dimensions & objective tiles
- Spawn count bounds per team
- BFS self‑path and neighbor shape

## Relay (optional, experimental)
A tiny Node WebSocket relay is provided to mirror chat/events across clients.

```bash
cd relay
npm install
npm start
# Server listens on ws://localhost:8080
```
Then paste `ws://localhost:8080` into the UI and click **Connect** on each client.

> The relay is intentionally minimal and **not** secure. For production, add auth, rooms, and rate limits.

## Project layout
```
team-strategy-grid/
├─ index.html        # the game (single file)
├─ README.md
├─ LICENSE           # MIT
├─ .gitignore
└─ relay/
   ├─ package.json
   └─ server.js      # minimal WebSocket relay
```

## License
MIT — see `LICENSE`.
