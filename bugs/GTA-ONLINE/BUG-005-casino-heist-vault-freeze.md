## BUG-005 — Casino heist: full game freeze during vault interaction

**game:** GTA Online
**platform:** PC, PS4, PS5
**build:** v1.50+ — been there since Diamond Casino Heist launched
**logged:** July 2024
**last checked:** November 2025
**source:** community (4 independent sources)
**severity:** SEV-1 | **priority:** P1 | **status:** OPEN

---

### what's happening

This is the worst one in the heist cluster. During the vault phase — either triggering the vault door or picking up loot from certain spots in the back section — the game can fully freeze. Not a crash to desktop. Frame stops, audio loops, nothing responds. Hard force-quit required.

You lose the entire heist when this happens. All prep costs gone. On console there are reports of save data weirdness after the hard restart but I can't confirm that happens consistently — just flagging it.

---

### when it happens

- vault door interaction (the hack/keycard/thermal depending on approach)
- loot pickups in the back-right section of the vault
- doesn't seem to be approach-specific, all three can hit this

---

### steps to reproduce

*(not deterministic)*

1. launch Casino Heist finale, any approach
2. get to the vault
3. trigger vault door interaction OR pick up loot from the back section
4. somewhere during or just after the interaction animation: full freeze
5. audio loops, no input works, have to force quit
6. heist is gone

---

### expected vs actual

**expected:** vault door opens, loot pickups complete, game keeps running
**actual:** game locks up completely mid-interaction. only recovery is force quit.

---

### reproducibility

low per-attempt rate — rough ballpark is maybe 1 in 15-20 vault runs, maybe less. but given how long heist runs are that's still a lot of people hitting it. no single trigger condition identified, seems to vary by session state.

---

### workaround

none. vault interaction is mandatory to finish the heist. keep task manager open on PC. on console you just have to hope.

---

### why this is SEV-1 and not SEV-2

full unrecoverable game freeze during a mandatory step, after spending 30-60+ mins and GTA$30k-150k+ in prep. that's the definition of critical regardless of how low the per-run rate is. and on console there's the save data risk on top of it.

---

### sources

- r/gtaonline — vault freeze reports going back to v1.50 launch
- GTA Forums — Casino Heist bug thread, vault freeze section
- YouTube — two screen recordings of the freeze mid-vault (reviewed)
- Rockstar Support community — ticket references
