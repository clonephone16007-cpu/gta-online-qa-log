## BUG-005 — Casino heist: game freezes completely during vault interaction

**game:** GTA Online  
**platform:** PC, PS4, PS5  
**build:** v1.50+ — present since Diamond Casino Heist launch  
**logged:** July 2024  
**last checked:** November 2025  
**source:** community-sourced (4 independent sources)  
**severity:** SEV-1  
**priority:** P1  
**status:** OPEN

---

### what's happening

This is the worst one in the Casino Heist cluster. During the vault phase of the heist finale, interacting with the vault door or certain loot positions inside the vault can trigger a full game freeze. Not a crash to desktop — the game just locks. Frame stops, audio loops, nothing responds. You have to force-close it (task manager on PC, hard restart on console in some cases).

When this happens you lose the entire heist. All prep costs, all the time investment, gone. On console there are cases of save data weirdness after a hard restart following one of these freezes, though I can't confirm that happens consistently.

---

### environment

- heist: Diamond Casino Heist finale, vault interaction phase
- trigger points: vault door interaction prompt, and specific loot pickup positions in the back section of the vault
- platform: PC + console
- crew size: any

---

### steps to reproduce

*(not deterministic — this documents the trigger window)*

1. complete heist prep and launch Diamond Casino Heist finale
2. navigate to the vault using your approach
3. trigger the vault door interaction (hack / keycard / thermal depending on approach)
4. alternatively: enter vault and approach loot positions in the back-right area
5. **what happens:** during or just after the interaction animation, game freezes. audio loops. no input works.
6. have to force quit. heist is lost.

---

### expected

Vault door unlocks normally. Loot pickups complete. Game stays functional throughout the vault sequence.

### actual

Game freezes during vault interaction. Unrecoverable without force quit. Full session loss including all prep.

---

### reproducibility

Roughly 5-10% per vault interaction. Low individual rate but — given how long a heist run takes — it happens frequently enough across the player base to be a significant issue. No single trigger condition identified; seems to vary by session state.

---

### workaround

None. The vault interaction is required to complete the heist. Can't skip it. Keep task manager open on PC. Hard restart risk on console if it freezes.

---

### why it's SEV-1

Full game freeze requiring force quit, during a mandatory gameplay step, resulting in permanent loss of 30-60+ mins of play time and GTA$30k-150k+ in prep costs. On console there's also a documented (if inconsistent) risk of save data issues from the hard restart. That combination is critical severity even at a 5-10% rate.

---

### sources

- r/gtaonline — ongoing reports of Casino Heist vault freeze since v1.50 launch
- GTA Forums — Casino Heist bug thread, vault freeze section
- YouTube — screen recordings of the freeze mid-vault interaction (2 clips reviewed)
- Rockstar Support community — ticket references for vault interaction freeze
