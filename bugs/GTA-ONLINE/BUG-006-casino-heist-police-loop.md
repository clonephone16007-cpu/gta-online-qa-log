## BUG-006 — Casino heist: wanted level loops after vault exit

**game:** GTA Online
**platform:** PC, PS4, PS5
**build:** v1.50+
**logged:** August 2024
**last checked:** October 2025
**severity:** SEV-3 | **priority:** P3 | **status:** OPEN

### what's happening

During the escape phase after the vault, the 5-star wanted level can get stuck in a loop. Stars flash on/off repeatedly like the alarm is re-triggering every few seconds. Police keep spawning in waves. Normal escape mechanics — breaking LoS, getting far enough away — don't work while it's looping.

Correlates with alerted runs (vault alarm triggered). Doesn't happen every alerted run but that's the common setup when it does.

### steps to reproduce

1. Casino Heist — Aggressive approach (always alerted) or S&S with triggered alarm
2. complete vault, head toward escape
3. watch the wanted level indicator during the escape
4. **might see:** stars cycle — fade out then immediately refill, on repeat
5. police dispatch every cycle, can't shake it

*happens maybe 1 in 3-4 alerted runs roughly, but I haven't tracked this one carefully*

### workaround

S&S without triggering the alarm avoids this entirely. Big Con disguise exit is supposed to skip the wanted phase too but that has its own issues (see BUG-007). Once the loop starts there's no mid-run fix.

### sources

- r/gtaonline — Jul-Sep 2024
- GTA Forums bug compilation
- YouTube — clip of the star cycling during escape
