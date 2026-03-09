# Story 3.1 — Adding Connections (SOUL Network)

**Epic:** Epic 3 — The Social Network (Post-Match)
**Story ID:** epic-3-story-1
**Status:** pending
**Priority:** High

## User Story
As a user, I want to add my chat partner to my SOUL Network so that we can message each other later.

## Acceptance Criteria
- [ ] AC1: Add to SOUL Network button becomes available after profile reveal
- [ ] AC2: Sending a SOUL mate Request notifies the other user
- [ ] AC3: Recipient can accept or decline the request
- [ ] AC4: On mutual acceptance, both users are added to each other persistent connection list
- [ ] AC5: Connected users appear in a dedicated Direct Messages list
- [ ] AC6: Declining a request is graceful — sender sees soft messaging not hard rejection
- [ ] AC7: Connection persists across sessions and app restarts

## Technical Notes (Atlas)
- connections table: (user_a_id, user_b_id, status, created_at) status: pending|accepted|declined
- REST: POST /connections (send request), PATCH /connections/:id (accept/decline)
- Push notification on request received (FCM/APNs)
- Direct Messages list queries connections where status=accepted

## UX Notes (Iris)
- Add button visually prominent post-reveal — not hidden behind menus
- Request sent confirmation: inline toast, not blocking modal
- DM list shows avatar, display name, last message preview
- Empty state: friendly illustration + Start chatting to make connections

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
| UX Review | Iris | pending |
