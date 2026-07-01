## BUG-002 — Mk2 special ammo randomly wipes to 0 on session change

**game:** GTA Online
**platform:** PC + console (community cross-platform reports)
**build:** v1.68+ — Rockstar acknowledged it exists
**logged:** March 2024
**last checked:** January 2026
**severity:** SEV-2 | **priority:** P2 | **status:** ACKNOWLEDGED (not fixed)

---

### what's happening

Special ammo on any mk2 weapon — explosive, hollow point, incendiary, AP, tracer, FMJ — can silently reset to 0 rounds after a session change. Standard ammo on the same weapon is fine. No notification, nothing in the log, just gone.

Rockstar have acknowledged this one exists but it's not fixed as of last check.

---

### environment

- weapons: all mk2 variants. most reports on carbine mk2 and pistol mk2 but others hit too
- trigger: any session transition — leave to story, find new session, exiting a job back to freemode
- platform: PC and console both

---

### steps to reproduce

1. buy a full stock of any special ammo on a mk2 weapon, note the count
2. leave the session (find new session, or leave gta online entirely)
3. rejoin
4. check the weapon wheel

sometimes it's fine. sometimes the special ammo is just gone. that's kind of the whole problem — it doesn't fail deterministically which makes it annoying to pin down.

---

### expected vs actual

**expected:** ammo count survives session changes
**actual:** special ammo wipes intermittently. standard ammo unaffected.

---

### reproducibility

Intermittent — doesn't happen on every transition. community reports put it somewhere in the 40-60% range across attempts but honestly I haven't tracked it that carefully myself, that figure is from aggregated reports. the randomness itself is the tell — points to a race condition in how inventory writes during session exit.

---

### workaround

none confirmed. avoid buying large stocks of expensive ammo right before you know you're switching sessions.

---

### sources

- r/gtaonline — multiple threads Feb 2024+
- Rockstar Support — acknowledged in official community thread
- GTA Forums — cross-platform thread documenting this
