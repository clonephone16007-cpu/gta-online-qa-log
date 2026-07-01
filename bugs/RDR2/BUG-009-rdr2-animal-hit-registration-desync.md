## BUG-009 — RDR2 Online: deer/buck don't react to headshots until you walk up to them

**game:** Red Dead Online
**platform:** PC (personally), PS4/PS5 in community reports too
**build:** can't correlate to a specific patch, showing up across multiple builds
**logged:** November 2024
**last checked:** still open / sourcing in progress
**severity:** SEV-3 | **priority:** P3 | **status:** WIP

> haven't moved this to OPEN yet. one source confirmed, waiting on a second before I treat it as solid. writing it up now so i don't lose the detail.

---

### what's happening

Shoot a deer or buck in the head at standard hunting range (~40-100m). Hit marker fires, reticle was on the head. Animal just... keeps grazing. No flinch, no blood, nothing.

Then you walk toward it and it drops dead when you get within maybe 10-15m.

So the kill registered on the server. It just didn't propagate back to the world state until proximity forced a sync. Animal was technically dead already, the game just hadn't caught up.

Practical problem: the animal can wander off before the state resolves. You're chasing a corpse that doesn't know it's dead yet. Also potentially screws with hunting challenges depending on how kill conditions are evaluated.

---

### how to see it

*(based on what i've found so far — treat as provisional)*

- RDO free roam
- find deer or buck at 40-100m
- bolt action or rolling block, aim for the head
- land the shot, hit marker confirms
- animal shows no reaction, keep watching
- walk toward it
- it collapses once you get within ~10-15m, loot prompt appears

---

### expected vs actual

**expected:** headshot kills on impact at any range within the weapon's effective distance
**actual:** kill registers server-side but world state doesn't update until proximity forces a sync. animal is in a "dead but doesn't know it" limbo.

---

### reproducibility

not sure yet. intermittent, seems like distance and latency are factors. need more attempts to get a real sense of the rate.

---

### workaround

after a no-reaction headshot just walk up to the animal quickly before it wanders. death registers within ~15m.

---

### notes

this is a pretty classic networked hit-reg pattern — client-side hit gets registered but server entity state doesn't sync back until proximity triggers it. worth writing up properly because most players would just assume they missed the shot.

---

### sources

- one community source confirmed (reddit, Nov 2024)
- still looking for independent second source
