# Story 2.1 — Interest-Based Roulette Match

**Epic:** Epic 2 — Core Chat & Matchmaking
**Story ID:** epic-2-story-1
**Status:** pending
**Priority:** Critical (core product feature)

## User Story
As a user, I want to tap "Find a Match" and connect with someone in under 5 seconds so that I do not get bored waiting.

## Acceptance Criteria
- [ ] AC1: Redis-backed matchmaking queue pairs users sharing at least 1 interest tag
- [ ] AC2: Match is established in under 5 seconds (p95 latency SLA)
- [ ] AC3: Fallback to 0-tag match after 10 seconds if no tag match found
- [ ] AC4: Skip button is visible and instantly disconnects current match
- [ ] AC5: Skipped users are not re-matched within the same session
- [ ] AC6: Loading/waiting animation shown during match search
- [ ] AC7: Connection established via WebSocket (Socket.io)

## Technical Notes (Atlas)
- Redis sorted set queue keyed by interest tags
- Socket.io room per match session, destroyed on skip/disconnect
- Match algorithm: intersect user tag sets, pick least-recently-matched partner
- Cold-start fallback: join global_queue after 10s timeout

## UX Notes (Iris)
- Find a Match button must be the primary CTA — large touch target (min 44px)
- Lottie animation during wait to reduce perceived wait time
- Skip button accessible via keyboard and screen reader
- Match found state: clear visual transition into chat view

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
| UX Review | Iris | pending |
