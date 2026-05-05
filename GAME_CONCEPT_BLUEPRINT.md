# Web/App .io-Style Game Blueprint

## 1) Core Idea (fill this in first)
- **Working title:**
- **One-line pitch:**
- **Genre:** (battle arena / survival / puzzle / social / idle / strategy)
- **Session length:** (e.g., 3–8 minutes)
- **Target players:** (casual mobile / competitive / kids / niche fandom)

---

## 2) Gameplay Loop
1. Player joins a match instantly (no friction).
2. Player collects/earns a resource (XP, mass, cards, coins).
3. Player upgrades in-match (speed, defense, power).
4. Player competes/cooperates with others.
5. Match ends with rank/reward.
6. Player spends rewards on progression/cosmetics.
7. Player queues again.

Keep this loop under 10 seconds per “interesting decision.”

---

## 3) MVP Scope (first playable)
### Must-have
- Guest login + nickname
- One map / arena
- 1 core mechanic (eat/collect/shoot/merge/etc.)
- Matchmaking for up to 20–50 players
- Basic leaderboard + end-of-match screen
- Simple progression (levels or unlocks)

### Nice-to-have (phase 2)
- Parties/friends
- Skins/emotes
- Seasonal quests
- Multiple game modes

---

## 4) Tech Stack Recommendation

## Option A: Fastest Web MVP
- **Frontend:** Phaser + React (or plain Phaser)
- **Realtime networking:** Colyseus / Socket.IO
- **Backend:** Node.js + TypeScript
- **Database:** PostgreSQL (accounts/progression), Redis (sessions)
- **Hosting:** Vercel (frontend) + Fly.io/Render (backend)

## Option B: Mobile-first + Web later
- **Client:** Unity (iOS/Android/WebGL)
- **Backend:** Nakama or custom Node/Go realtime service
- **Pros:** Better for complex gameplay and app stores
- **Cons:** Slower iteration than web-first

---

## 5) System Architecture (simple)
- **Client:** input prediction + interpolation
- **Game server:** authoritative simulation at fixed tick rate (20–30 ticks/sec)
- **API server:** auth, inventory, progression
- **Analytics:** events for retention and balance tuning

### Core backend services
- Matchmaker
- Room server
- Profile service
- Economy service
- Anti-cheat checks (server-side validation)

---

## 6) Monetization (non-pay-to-win)
- Cosmetic skins, trails, emotes
- Battle pass (cosmetic-focused)
- Rewarded ads (optional)
- Starter bundle (cosmetic + convenience)

Avoid selling direct stat power if PvP is central.

---

## 7) 6-Week Build Plan

### Week 1
- Finalize game loop + controls
- Implement single-player sandbox

### Week 2
- Add realtime multiplayer room
- Basic movement/combat sync

### Week 3
- Match start/end flow + leaderboard
- Persistent profiles + progression

### Week 4
- Mobile responsive UI
- Basic cosmetics + shop mock

### Week 5
- Analytics + balancing pass
- Bug fixing + performance optimization

### Week 6
- Closed alpha (50–200 players)
- Patch top issues + publish beta

---

## 8) Product Metrics to Track
- D1 / D7 retention
- Avg session length
- Matches per user/day
- Conversion to account creation
- Crash rate and ping distribution
- Match completion rate

---

## 9) Immediate Next Actions
1. Write your one-line pitch and target audience.
2. Pick Option A (web MVP) or Option B (mobile-first).
3. Define one unique mechanic and one fail condition.
4. Build prototype with bots before full multiplayer load.

---

## 10) Prompt You Can Reuse with AI/Devs
"Design a multiplayer .io-style game with a 5-minute session loop for [audience].
Core mechanic: [mechanic].
Progression: [meta system].
Provide:
- technical architecture,
- data model,
- anti-cheat strategy,
- matchmaking rules,
- week-by-week implementation plan,
- and launch checklist."
