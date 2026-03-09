# Story 2.3 — The Profile Reveal

**Epic:** Epic 2 — Core Chat & Matchmaking
**Story ID:** epic-2-story-3
**Status:** pending
**Priority:** High

## User Story
As a user, I want to reveal my full photos and social feed only after a good conversation so that I can filter out creeps before they see my content.

## Acceptance Criteria
- [ ] AC1: Reveal Profile button is locked (disabled) for the first 5 minutes of active messaging
- [ ] AC2: Button unlocks after 5 minutes of active messaging (messages sent by both users)
- [ ] AC3: User A initiates reveal — User B receives a consent notification
- [ ] AC4: Reveal only completes when BOTH users accept (mutual consent required)
- [ ] AC5: If User B declines, User A is notified gracefully with soft messaging
- [ ] AC6: On mutual reveal, full profile photos and social feed become visible in chat
- [ ] AC7: Reveal state is persisted — re-opening chat does not hide profiles again

## Technical Notes (Atlas)
- Server-side timer tracking active message count per session
- chat_sessions table: (id, user_a, user_b, started_at, reveal_unlocked_at, reveal_status)
- reveal_status enum: locked, unlocked, pending_b, revealed, declined
- Socket.io events: reveal_request, reveal_consent, reveal_declined, reveal_complete

## UX Notes (Iris)
- Timer countdown visible to both users as subtle progress indicator
- Reveal request notification must be non-intrusive (banner not modal)
- Decline flow: soft messaging — "They are not ready yet" not "Rejected"
- Consent prompt must have clear Accept / Not Yet actions (not Accept / Reject)

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
| UX Review | Iris | pending |
