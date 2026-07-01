## BUG-001 — Carbine Rifle suppressor: off-radar state + audio doesn't reset after long session

**game:** GTA Online  
**platform:** PC  
**build:** v1.68+ (Los Santos Drug Wars) — still present in recent patches  
**logged:** January 2024  
**last checked:** March 2026  
**source:** personal — reproduced myself across multiple sessions  
**severity:** SEV-2  
**priority:** P2  
**status:** OPEN

---

### what's happening

The carbine rifle (standard and mk2) has a suppressor attachment that gives you a temporary off-radar effect while firing. That's intended — it's supposed to drop off ~3-5 seconds after you stop shooting.

After a long session (usually 60-90+ mins of continuous play) that off-radar state stops clearing properly. It just... stays. You're off the radar permanently without firing, and the suppressed audio stays on too. It survives going into missions, entering interiors, all of it. The only thing that actually fixes it is swapping off the weapon or leaving the session entirely.

I noticed this first during a long freemode grind session in Jan 2024. Thought I was imagining it at first, then reproduced it intentionally a few more times.

---

### environment

- platform: PC (Steam)
- session type: public free roam
- session length when it triggers: 60-90+ mins
- weapon: carbine rifle / carbine rifle mk2, suppressor equipped
- happened on two different characters

---

### steps to reproduce

1. join a public free roam session
2. equip carbine rifle or carbine mk2 with suppressor on
3. stay in session, do normal freemode stuff — missions, grinding, whatever. key thing is staying in the same session for 60+ mins
4. after about an hour, start paying attention to your radar when you fire the suppressed carbine
5. fire a few shots, then stop
6. watch the minimap — the off-radar blip should come back within a few seconds
7. **what happens instead:** off-radar doesn't clear. you stay invisible on the map even after stopping
8. go enter an interior or join a quick job to cause a soft transition
9. come back out — still off radar. audio still suppressed.

note: doesn't happen every single time, but in sessions over 60 mins I'd say it triggers roughly 70% of the time

---

### expected

Off-radar effect clears ~3-5 seconds after last shot. Audio goes back to normal. Session transitions don't affect weapon state.

### actual

Off-radar stays locked on. Weapon audio stays suppressed. Persists through soft transitions. Only clears on weapon re-equip (sometimes) or full session exit.

---

### reproducibility

~70% in sessions 60+ mins long. Reproduced personally in 4+ separate sessions. Have seen community posts corroborating this on PC and mentions of it on console too but I can only confirm PC personally.

---

### workaround

Swap to a different weapon and back — fixes it maybe 85% of the time. If that doesn't work, exit to story mode and rejoin. That always clears it.

---

### why it matters

Permanent off-radar without actively suppressor-firing is a pretty significant PvP advantage in public sessions. Not game-breaking but it's exploitable and it's definitely unintended. The audio side of it also messes with spatial awareness — you lose the audio cue difference between suppressed and unsuppressed fire.

My guess is it's a session-duration memory issue — something in how the suppressor state flag gets tracked accumulates over long sessions and stops clearing properly. The mk2 version seems to trigger it slightly more often than standard, which might mean the extra weapon flags from the mk2 system are involved somehow.

---

### sources

- personal reproduction (jan 2024 – mar 2026, 4+ sessions)
- r/gtaonline threads with multiple users reporting same suppressor state issue, jan-mar 2024
- rockstar support community — ticket threads on carbine suppressor audio anomalies post-v1.68
