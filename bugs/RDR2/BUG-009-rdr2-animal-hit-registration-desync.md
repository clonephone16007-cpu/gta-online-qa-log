## BUG-009 — RDR2 Online: deer/buck don't react to headshots until you get close

**game:** Red Dead Online  
**platform:** PC primary focus, community reports on PS4/PS5 too  
**build:** no specific patch correlation found, appears in multiple builds  
**logged:** November 2024  
**last checked:** ongoing — still sourcing  
**source:** community research, sourcing in progress  
**severity:** SEV-3  
**priority:** P3  
**status:** WIP — still documenting, one source confirmed, need second

---

> **note:** this report isn't finished. I have one solid source and the behaviour pattern is clear from research, but I'm not moving it from WIP to OPEN until I have a second independent source confirming the same thing. documenting progressively so the detail doesn't get lost.

---

### what's happening

In Red Dead Online, deer and buck sometimes show zero reaction to a confirmed headshot from standard hunting range (~40-100m). Hit marker fires, reticle was on the head, the shot clearly connected — but the animal doesn't flinch, collapse, or show any blood effect. It just keeps doing what it was doing.

Then you walk toward it. Get within maybe 10-15 metres. And it drops dead.

The kill was already registered server-side, it just didn't update the world state until your proximity triggered a sync. The animal was technically already dead; the visual/game state just hadn't caught up.

This is annoying for a few reasons: the animal can move before the kill state resolves, so you end up chasing a dead deer. Also messes with hunting challenges if the kill condition requires something specific about the death.

---

### environment

- game: Red Dead Online — Free Roam
- animals: deer and buck confirmed, possibly other mid-size prey
- shot type: headshot, confirmed via hit marker
- distance: roughly 40-100m
- suspected factor: server latency / network state

---

### steps to reproduce

*(based on current research — subject to revision)*

1. Red Dead Online free roam
2. find a deer or buck at ~40-100m range
3. aim with a rifle that one-shots on headshot (bolt action, rolling block etc.)
4. land a headshot — hit marker confirms the shot
5. **watch:** animal shows no reaction. keeps moving/grazing.
6. wait 5-10 seconds at current distance. still alive-looking.
7. move toward the animal, close to ~10-15m
8. **animal collapses.** loot prompt appears. kill registered retroactively.

---

### expected

Headshot at any distance within effective weapon range kills the animal immediately. Collapse happens on impact. Death state visible regardless of player distance.

### actual

Kill is registered but world state doesn't update until player closes in. Animal exists in a "dead but world doesn't know yet" state. Proximity forces the sync and the collapse finally plays.

---

### reproducibility

Unknown rate — still researching. Intermittent. Distance and network conditions seem to be factors.

---

### workaround

After a no-reaction headshot, move toward the animal before it wanders. Death usually registers once you're within ~15m. Keep shot distance below 40m if possible to reduce the desync window.

---

### notes

This fits a known pattern in networked game hit registration — client registers the hit, server-side entity state doesn't propagate back until proximity forces a state sync. Worth flagging because it's subtle enough that most players would assume they missed rather than identifying it as a hit-reg desync.

That's also why I think it's worth documenting properly even though it's WIP — the behaviour description is solid even if the sourcing isn't complete yet.

---

### sources

- community research — initial identification via Reddit and forum reports (Nov 2024), one source confirmed
- second independent source: still searching
