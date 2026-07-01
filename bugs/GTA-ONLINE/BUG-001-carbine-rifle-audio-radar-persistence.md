## BUG-001 — Carbine Rifle suppressor: off-radar state + audio stuck after long session

**game:** GTA Online
**platform:** PC (Steam)
**build:** v1.68+ — still showing up in recent patches
**logged:** January 2024
**last checked:** March 2026
**source:** personal, reproduced multiple times
**severity:** SEV-2 | **priority:** P2 | **status:** OPEN

---

### what's happening

The suppressor on the carbine (standard + mk2) is supposed to give you a temporary off-radar window while firing, then drop ~3-5s after you stop. That's normal and intended.

Problem: after a long session — usually somewhere past the 60-90 min mark — that off-radar state just stops clearing. You stay invisible on the map even when you're not firing. Audio stays suppressed too. It survives mission loads, interior transitions, all of it. Only things that actually fix it are weapon swap or leaving the session.

First noticed this in Jan 2024 during a long freemode grind. Thought I was imagining it. Reproduced it intentionally maybe 4-5 times since.

---

### environment

- platform: PC (Steam)
- session type: public free roam
- session duration at trigger: 60+ mins, usually closer to 90
- weapon: carbine rifle or carbine mk2, suppressor attached
- two different characters, same result

---

### steps to reproduce

1. join public free roam
2. equip carbine (standard or mk2) with suppressor
3. just play normally — missions, grinding, whatever — stay in the same session for 60+ mins
4. at some point start watching the minimap after you fire the suppressed carbine
5. fire a burst, stop shooting, wait
6. **off-radar blip doesn't come back.** stays cleared even standing still doing nothing
7. enter an interior or join a contact mission to force a soft transition
8. come back to freemode — still off radar

note: mk2 version seems to trigger it slightly more often than standard, not sure if that's real or just confirmation bias on my end

---

### expected vs actual

**expected:** off-radar clears 3-5s after last shot, always
**actual:** state gets stuck on after ~60+ min sessions, persists through transitions, only clears on weapon swap or session exit

---

### reproducibility

happens most of the time in sessions over an hour. not 100% — maybe misses once every few attempts. hard to be precise because you can't really force the exact session state that causes it.

---

### workaround

swap to any other weapon and back — works most of the time. if that doesn't clear it, exit to story mode and rejoin. that always fixes it.

---

### notes

pretty sure this is a session-duration memory thing — like the suppressor state flag accumulates over a long session and something stops resetting it properly. the mk2 triggering more often might point to the extra weapon flags it uses vs standard.

not game-breaking but it is a genuine unintended PvP advantage in public lobbies — permanent off-radar without actively firing is pretty significant.

---

### sources

- personal repro (jan 2024 – mar 2026)
- r/gtaonline — a few threads from jan-mar 2024 with other people hitting the same thing
- rockstar support forum — ticket threads on carbine suppressor audio anomalies post-v1.68
