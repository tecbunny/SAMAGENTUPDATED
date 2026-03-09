# Story 4.1 — Instant Block and Report

**Epic:** Epic 4 — Privacy, Safety and Moderation
**Story ID:** epic-4-story-1
**Status:** pending
**Priority:** Critical (safety — launch blocker)

## User Story
As a user, I want to block and report inappropriate users with one tap so that I am protected from harassment.

## Acceptance Criteria
- [ ] AC1: A Shield icon is visible in the top-right of every active chat screen
- [ ] AC2: Tapping Shield presents options: Block, Report, Cancel
- [ ] AC3: Selecting Report immediately disconnects the chat
- [ ] AC4: Report logs the full chat transcript for admin review
- [ ] AC5: Reported user is blocked automatically upon report submission
- [ ] AC6: Blocked users can never be matched with the reporting user again
- [ ] AC7: Report submission confirms to user with Report received message
- [ ] AC8: Block list is persistent across sessions

## Technical Notes (Atlas)
- reports table: (id, reporter_id, reported_id, transcript, reason, created_at)
- blocks table: (blocker_id, blocked_id, created_at) — composite primary key
- Matchmaking queue must exclude blocked pairs before assignment
- Chat transcript stored as JSONB in reports table
- REST: POST /reports, POST /blocks

## UX Notes (Iris)
- Shield icon: minimum 44px touch target, high contrast, always visible
- Action sheet (not dialog) — native feel on mobile
- Report confirmation: green toast Your report has been received. User blocked.
- No identity of reporter ever shown to reported user

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
| UX Review | Iris | pending |
