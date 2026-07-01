## BUG-006 — Casino heist: police wanted level loops on repeat after vault exit

**game:** GTA Online  
**platform:** PC, PS4, PS5  
**build:** v1.50+  
**logged:** August 2024  
**last checked:** October 2025  
**source:** community-sourced (3 sources verified)  
**severity:** SEV-3  
**priority:** P3  
**status:** OPEN

---

### what's happening

After the crew exits the vault during the Casino Heist escape phase, the police wanted level can get into a loop state. Instead of staying at 5 stars and responding normally to escape behaviour, the stars flash on and off repeatedly — like the game is constantly re-triggering the alarm condition. Police keep getting dispatched in waves, and standard escape mechanics (outrunning them, losing line of sight) don't work while the loop is active.

Seems to correlate with runs where the vault alarm was triggered. Not every alerted run causes this, but it's the common setup when it does happen.

---

### environment

- heist: Diamond Casino Heist finale, escape phase
- phase: after vault exit, moving toward exit point
- trigger condition: vault alarm triggered during heist
- approaches affected: all, but most common with Aggressive (alarm is always active) and S&S with triggered alarm

---

### steps to reproduce

1. Diamond Casino Heist — use Aggressive approach (wanted level active from start) or trigger the alarm in Silent & Sneaky
2. complete vault phase
3. exit vault and head toward escape exit
4. watch wanted level indicator
5. **what happens:** 5-star indicator starts cycling — fades and refills rapidly in a loop instead of holding steady at 5 stars
6. police continue being dispatched every cycle regardless of what you do
7. trying to escape doesn't reduce stars while loop is active

---

### expected

Wanted level holds at 5 stars after vault exit. Standard escape mechanics apply — break line of sight, reach escape range, stars reduce normally.

### actual

Wanted level loops. Police re-dispatch every cycle. Can't clear stars through normal escape. Either have to reach an exit that bypasses the wanted level system or get killed.

---

### reproducibility

~25-35% in heist runs with triggered vault alarm. The alarm state seems to be the main contributing factor, but it doesn't happen every alerted run.

---

### workaround

Play Silent & Sneaky without triggering the alarm to avoid the condition entirely. The Big Con exit disguise is supposed to bypass the wanted level phase (but see BUG-007 for that failing too). No fix once the loop starts mid-session.

---

### sources

- r/gtaonline — reports of wanted level looping during Casino Heist escape, Jul-Sep 2024
- GTA Forums — Casino Heist bug compilation entry
- YouTube — gameplay showing police star cycling during heist escape
