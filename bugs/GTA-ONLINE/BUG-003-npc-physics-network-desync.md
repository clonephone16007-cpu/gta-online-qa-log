## BUG-003 — Desynced NPC cars sending player ragdoll way too far

**game:** GTA Online
**platform:** PC + console
**build:** started noticing post-v1.66 (E&E NPC physics update)
**logged:** May 2024
**last checked:** December 2025
**source:** community (reddit + yt footage)
**severity:** SEV-3 | **priority:** P3 | **status:** OPEN

---

### what's happening

In public sessions, if you get clipped by an NPC vehicle that's in a desync state — you can usually tell, they're stuttering or teleporting slightly — the collision physics completely loses the plot. Instead of a proportional hit reaction you just get launched. Like full truck-speed impact from a car that was barely moving.

The client-side part is what makes it obvious it's a bug: other players in the same session see a normal-ish collision on their screen while you're watching yourself fly 30 meters. Your game is applying the wrong physics model because the NPC's state is desynced from the server.

Started being noticeable after the v1.66 physics update. My guess is the updated and old pre-patch physics models can conflict when a vehicle is in a bad network state, and your client just picks one at random basically.

---

### how to see it

*(can't reproduce on demand, depends on NPC network state)*

- join a high-latency public session — higher latency = more desynced NPCs
- watch traffic for vehicles acting wrong: stuttering, slight teleporting, clipping through props
- get near one of those vehicles on foot or in a car
- if it clips you: ragdoll is wildly out of proportion to the actual impact
- confirm with another player — they usually see nothing weird on their end

---

### expected vs actual

**expected:** collision force proportional to NPC vehicle speed/mass
**actual:** client applies old physics coefficients to the desynced vehicle, hit registers as much higher mass/velocity than real. only happens on that client.

---

### reproducibility

happens a fair amount in chaotic high-latency public sessions. can't put a reliable number on it because you can't control whether a desynced NPC is nearby. invite-only sessions don't have the desync condition so it doesn't happen there.

---

### workaround

stay out of NPC traffic in crowded public sessions. invite-only removes the condition entirely.

---

### sources

- r/gtaonline — "NPC cars sending me flying" threads Apr-Jun 2024, multiple independent reports
- YouTube — two clips showing the disproportionate ragdoll from NPC hits
- GTA Forums — physics regression thread post-E&E update
