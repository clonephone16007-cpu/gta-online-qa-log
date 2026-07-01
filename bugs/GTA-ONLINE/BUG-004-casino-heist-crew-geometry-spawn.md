## BUG-004 — Casino heist: crew member spawns inside a wall at heist start

**game:** GTA Online  
**platform:** PC, PS4, PS5  
**build:** v1.50+ — Diamond Casino Heist, all approaches  
**logged:** July 2024  
**last checked:** October 2025  
**source:** community-sourced (3 sources verified)  
**severity:** SEV-3  
**priority:** P3  
**status:** OPEN

---

### what's happening

At the start of the Diamond Casino Heist finale, one crew member (usually in a 4-player lobby) spawns inside wall geometry instead of at a proper spawn point. They're alive, camera works, but they literally cannot move. Stuck for the whole heist unless you restart.

This seems to affect the 3rd or 4th player in the lobby assignment order most often, but it's not perfectly consistent. Happens across all three approaches (silent & sneaky, aggressive, big con).

---

### environment

- heist: Diamond Casino Heist finale, all approaches
- crew size: mostly reported with 4-player crews, less common with 2
- platform: PC + console

---

### steps to reproduce

*(low reproduction rate — this is the setup that increases probability)*

1. set up Casino Heist finale with a full 4-player crew
2. assign roles — two primaries, two support
3. launch the finale
4. at the initial spawn sequence, watch all four spawn points
5. **what happens:** one player (typically 3rd or 4th assigned) appears inside geometry — inside a wall, pillar, or clipped below floor level
6. that player is stuck. can look around but can't move, sprint, or interact with anything
7. rest of the crew proceeds normally. heist technically continues

---

### expected

All four crew members spawn at accessible positions at the heist start. Everyone can immediately move and play.

### actual

One player spawns inside geometry. Effectively removed from the heist unless session is restarted. No way to self-recover from inside the geometry.

---

### reproducibility

~15-20% in 4-player heist runs. Not deterministic — can't force it. Running with 2 players seems to reduce it significantly.

---

### workaround

If you see someone spawn stuck, restart the heist immediately rather than continuing. Running 2-player reduces but doesn't eliminate the chance. No mid-session fix exists — the stuck player cannot recover themselves.

---

### sources

- r/gtaonline — multiple reports Jun-Aug 2024 of crew geometry spawns in Casino Heist finale
- GTA Forums — Casino Heist bug compilation thread
- YouTube — gameplay clips showing player stuck in spawn geometry at heist start
