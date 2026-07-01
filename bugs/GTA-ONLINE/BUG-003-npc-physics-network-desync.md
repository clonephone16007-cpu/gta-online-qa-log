## BUG-003 — Desync'd NPC vehicles make player ragdoll like they got hit by a bus

**game:** GTA Online  
**platform:** PC, PS4/PS5  
**build:** noticed post-v1.66 (after the E&E NPC physics update)  
**logged:** May 2024  
**last checked:** December 2025  
**source:** community-sourced (cross-verified — reddit + youtube footage)  
**severity:** SEV-3  
**priority:** P3  
**status:** OPEN

---

### what's happening

In public sessions, if you get hit by an NPC vehicle that's in a desync'd/glitched state (you can usually tell — they're stuttering, teleporting slightly, moving weird), the collision physics on your character goes completely wrong. Instead of a normal hit reaction proportional to the car's speed and mass, you get launched like you were hit by a truck doing 100mph even if the car was barely moving.

The weird part: other players in the same session don't see you get hit the same way you experience it. So it's client-side — your game is applying the wrong physics model to the collision because the NPC's state is desynced from the server.

This started being noticeable after the v1.66 physics updates to NPC vehicles. Seems like the updated physics model and the old pre-patch model can conflict when a vehicle is in a bad network state.

---

### environment

- platform: PC + console
- session type: public free roam (higher-latency sessions seem worse)
- trigger: getting hit by an NPC vehicle in a desync'd/glitched state
- player condition: on foot or in a vehicle, both affected

---

### steps to reproduce

*(can't reproduce on demand — depends on NPC state)*

1. join a public free roam session — higher latency = higher chance of seeing this
2. watch NPC vehicle traffic. look for vehicles acting wrong: stuttering, teleporting short distances, clipping through things
3. let one of those vehicles hit you (on foot or in a car)
4. **what happens:** ragdoll goes completely disproportionate — you get flung way further than the collision should produce, or the ragdoll loops longer than normal
5. check with other players in session — they often don't see the same collision on their screen

---

### expected

Collision response is proportional to NPC vehicle speed and mass at point of impact. Consistent with how physics normally work in the session.

### actual

Collision triggers a ragdoll using what looks like the pre-v1.66 physics coefficients — much higher effective mass/velocity applied to the NPC vehicle. Only the affected player experiences it this way; it's client-side.

---

### reproducibility

Around 30-50% in high-latency public sessions. Not controllable — depends on whether there's a desync'd NPC nearby and you end up in contact with it. Hard to test systematically because the trigger condition isn't something you can force.

---

### workaround

Avoid walking near NPC traffic in chaotic public sessions. Using invite-only removes the network desync condition and this doesn't happen. No in-session fix.

---

### sources

- r/gtaonline — threads around "NPC cars sending me flying for no reason" topic, multiple reports Apr-Jun 2024
- YouTube — two independent gameplay clips showing the disproportionate ragdoll from NPC hits
- GTA Forums — physics regression thread post-E&E update
