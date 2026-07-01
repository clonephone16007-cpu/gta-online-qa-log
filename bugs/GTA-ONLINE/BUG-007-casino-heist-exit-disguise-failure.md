## BUG-007 — Casino heist big con: exit disguise randomly blows for no reason

**game:** GTA Online
**platform:** PC, PS4, PS5
**build:** v1.50+
**logged:** August 2024
**last checked:** November 2025
**source:** community (3 sources)
**severity:** SEV-2 | **priority:** P2 | **status:** OPEN

> still not 100% sure on the trigger condition. the rate is hard to pin down. documenting what i know so far.

---

### what's happening

Big Con — whole point of the approach is you walk out in disguise and the wanted level doesn't trigger. Gruppe Sechs or Yung Ancestor outfit, game is supposed to suppress detection while you head to the exit.

Sometimes mid-walkout, doing nothing wrong, a wanted level just appears. 1-2 stars then escalates. Police respond like the disguise isn't active at all. The clean exit that people chose this approach specifically for just falls apart.

Suspect it's something to do with NPC proximity or a specific detection zone inside the Casino but nobody's nailed the exact condition. Could also just be a state bug where the disguise flag drops randomly, not sure.

---

### steps to reproduce

1. Big Con, either disguise
2. complete vault, start the exit walkout
3. move calmly toward the exit — no weapons out, no running, nothing that should break cover
4. **intermittently:** wanted stars appear mid-walk
5. escalates to 5 and you're now in a full escape run instead of a clean exit

*I've seen people say staying away from security NPCs helps but I haven't tested this enough to confirm it. could just be placebo.*

---

### expected vs actual

**expected:** disguise suppresses detection for the full walkout
**actual:** disguise condition drops mid-walkout with no player action that should trigger it

---

### workaround

go straight to the exit, don't deviate. if it fails anyway: have a vehicle close. you can't re-activate the disguise once it's blown.

---

### sources

- r/gtaonline — "big con disguise getting blown" threads Jul-Oct 2024
- GTA Forums — Big Con bug section
- YouTube — two clips of disguise failure during walkout
