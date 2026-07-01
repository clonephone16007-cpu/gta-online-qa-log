## BUG-002 — Mk2 special ammo resets to zero when changing sessions

**game:** GTA Online  
**platform:** PC, PS4/PS5 (community reports across platforms)  
**build:** v1.68+ — Rockstar has acknowledged this one  
**logged:** March 2024  
**last checked:** January 2026  
**source:** community-sourced (3 independent sources verified)  
**severity:** SEV-2  
**priority:** P2  
**status:** ACKNOWLEDGED — Rockstar confirmed, not fixed as of last check

---

### what's happening

Any mk2 weapon loaded with special ammo (hollow point, explosive, incendiary, AP, FMJ, tracer) can randomly wipe to 0 rounds when you change sessions. Not every time — that's what makes it annoying to pin down. But it happens often enough that people have lost huge amounts of expensive ammo with no explanation and no refund.

The standard ammo on the same weapon is fine. Only the special ammo gets wiped.

---

### environment

- platform: PC + console (cross-platform issue based on community reports)
- weapons affected: all mk2 variants — most reported with pistol mk2 and carbine mk2
- ammo types: all special ammo types
- trigger: session change (leaving to story mode, rejoining, exiting a job back to freemode)

---

### steps to reproduce

1. buy special ammo for any mk2 weapon from gun van or ammo counter — buy a full stock so you have a clear before/after to compare
2. note the ammo count in the weapon wheel
3. leave the session (pause menu → find new session, or leave gta online)
4. rejoin any session type
5. open weapon wheel, check your mk2 special ammo count

**what happens:** some percentage of the time, the count is 0. Standard ammo unchanged.

This is intermittent — doesn't happen every single transition. That makes it hard to reproduce on demand, but the community documentation on it is solid. Rockstar themselves have acknowledged it exists.

---

### expected

Ammo count persists across session changes. If you had 200 explosive rounds before leaving, you have 200 after rejoining.

### actual

Special ammo count drops to 0 on some session transitions. No notification, no explanation, no refund. Standard ammo unaffected.

---

### reproducibility

Intermittent — roughly 40-60% of session transitions based on aggregated community reports. The inconsistency itself is a data point — it points to something like a race condition in how inventory state gets written during session exit rather than a deterministic failure.

---

### workaround

None confirmed. Some people say buying a small extra amount of ammo right before leaving helps, but that's not verified. Honestly the only real mitigation is not buying large stocks of special ammo if you're about to change sessions.

---

### why it matters

Special ammo is expensive. Explosive rounds are around $500/round — losing 250 rounds is ~$125k GTA with no warning and no way to get it back. Directly affects player economy in a way that's both unintended and frustrating.

---

### sources

- r/gtaonline — multiple threads from Feb 2024 onwards
- Rockstar Support community — acknowledged in official support thread (referenced in r/gtaonline community)
- GTA Forums — cross-platform documentation thread
