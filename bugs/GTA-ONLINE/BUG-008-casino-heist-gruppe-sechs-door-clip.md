## BUG-008 — Casino heist: Gruppe Sechs entry door clips player

**game:** GTA Online  
**platform:** PC, PS4, PS5  
**build:** v1.50+  
**logged:** September 2024  
**last checked:** September 2025  
**source:** community-sourced (2 sources verified)  
**severity:** SEV-3  
**priority:** P3  
**status:** OPEN

---

### what's happening

During the Diamond Casino Heist Big Con approach using Gruppe Sechs, the service entrance door has a collision issue. When you trigger the entry interaction and try to walk through as the door opens, the door geometry can block you — the collision model on the door is active during its opening animation, so you hit it while it's still swinging open. In some cases you partially clip into the door geometry and get briefly stuck.

It's not catastrophic — backing up and retrying usually works after 1-2 attempts — but it disrupts the entry flow and looks broken.

---

### environment

- heist: Diamond Casino Heist — Big Con, Gruppe Sechs entry only
- phase: Casino entry sequence (before vault navigation)
- location: Gruppe Sechs service entrance door

---

### steps to reproduce

1. Diamond Casino Heist — Big Con, Gruppe Sechs entry
2. approach the Casino service entrance
3. trigger the door interaction
4. immediately try to walk through as the animation starts
5. **case A:** you collide with the door mid-animation and bounce back, can't pass through
6. **case B:** you partially clip into the door and get stuck briefly — can't move forward or back without manually backing away
7. retry usually gets you through after 1-2 attempts

---

### expected

Door animation completes, collision model either leads or matches the visual, player walks through cleanly.

### actual

Door collision is active during the swing animation. Player collides with a door that's visually opening but physically still blocking the space. Can cause a brief stuck state.

---

### reproducibility

~20-25% of Gruppe Sechs entry attempts. Walking into the door immediately after triggering the animation seems to increase the rate — waiting a beat for the animation to progress reduces it.

---

### workaround

Wait a moment after triggering the door interaction before walking through — let the animation get partway through before moving. If you clip: back away and retry. Usually resolves in 1-2 attempts.

---

### sources

- r/gtaonline — Gruppe Sechs door blocking reports, Aug-Oct 2024
- GTA Forums — Casino Heist entry door clipping thread
