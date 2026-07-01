## BUG-007 — Casino heist big con: exit disguise randomly stops working

**game:** GTA Online  
**platform:** PC, PS4, PS5  
**build:** v1.50+  
**logged:** August 2024  
**last checked:** November 2025  
**source:** community-sourced (3 independent sources)  
**severity:** SEV-2  
**priority:** P2  
**status:** OPEN

---

### what's happening

The Big Con approach's whole point is that you walk out of the Casino in disguise and the wanted level doesn't trigger. Gruppe Sechs uniform or Yung Ancestor outfit — the game is supposed to suppress detection while you walk to the exit.

This bug causes that suppression to fail intermittently. Mid-walk-out, with no aggressive action taken, a wanted level gets applied to one or more crew members. The police response triggers like the disguise condition isn't active at all. The entire strategic advantage of the Big Con approach is gone in one moment.

From the community reports it seems like NPC proximity or something in the Casino's detection zone can break the disguise condition even when nothing the player does should trigger it.

---

### environment

- heist: Diamond Casino Heist — Big Con approach only
- disguise type: Gruppe Sechs and Yung Ancestor both affected
- phase: exit walk-out sequence (heading toward Casino entrance/exit in disguise)
- suspected trigger: NPC proximity or specific detection zone during walk-out

---

### steps to reproduce

1. Diamond Casino Heist — Big Con approach, either disguise
2. complete vault phase
3. begin the exit walk-out in disguise — moving calmly toward exit, no weapons, no running
4. **what happens (intermittently):** wanted level appears mid-walk. 1-2 stars initially, sometimes escalating to 5 before reaching exit
5. police response triggers as if disguise is inactive
6. crew forced into combat/escape instead of clean exit

---

### expected

Disguise suppresses all wanted detection during the walk-out. Crew reaches exit without police interaction. Wanted level doesn't activate until disguise is intentionally broken or after natural exit.

### actual

Disguise fails. Wanted level appears without any player action that should break cover. The approach's core mechanic — the clean exit — fails due to a system error rather than player mistake.

---

### reproducibility

~20-30% of Big Con runs. Inconsistent trigger, suspected NPC or zone-based, but no one has pinned down the exact condition.

---

### workaround

Move directly to exit without stopping or deviating. Avoid getting too close to security NPCs during walk-out. If disguise fails: fall back to combat escape, have vehicles positioned close. No way to re-activate the disguise mid-mission once it's blown.

---

### why it matters

People specifically choose the Big Con approach to avoid the 5-star escape phase. When this triggers, they get exactly what they were trying to skip, through no fault of their own. That's a meaningful failure of a core gameplay mechanic in a high-investment activity.

---

### sources

- r/gtaonline — "big con disguise getting blown" threads, Jul-Oct 2024
- GTA Forums — Casino Heist Big Con bug documentation
- YouTube — footage of disguise failure during walk-out (2 independent clips reviewed)
