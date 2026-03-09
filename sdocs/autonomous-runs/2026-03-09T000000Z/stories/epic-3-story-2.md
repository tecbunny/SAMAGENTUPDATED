# Story 3.2 — SOUL Moments (Stories)

**Epic:** Epic 3 — The Social Network (Post-Match)
**Story ID:** epic-3-story-2
**Status:** pending
**Priority:** Medium

## User Story
As a user, I want to post 24-hour photo/text updates so that my newly made friends can see what I am up to.

## Acceptance Criteria
- [ ] AC1: A horizontal Moments feed is displayed at the top of the main social feed
- [ ] AC2: Moments feed shows only connections active (less than 24hr) Moments
- [ ] AC3: User can post a Moment with photo and/or text content
- [ ] AC4: Moments automatically expire and are removed after 24 hours
- [ ] AC5: User can reply to a Moment, which opens a persistent DM thread
- [ ] AC6: Own Moment is displayed first in the feed with a + add button
- [ ] AC7: Viewed/unviewed state is tracked per Moment per viewer

## Technical Notes (Atlas)
- moments table: (id, user_id, media_url, text, created_at, expires_at)
- expires_at = created_at + 24h — background cron job deletes expired rows
- Media uploaded to AWS S3, URL stored in moments table
- moment_views table: (moment_id, viewer_id, viewed_at) for view tracking
- Reply creates a DM: POST /messages with moment_id reference

## UX Notes (Iris)
- Horizontal scroll feed with circular avatar thumbnails
- Unviewed moments: coloured ring; Viewed: grey ring
- Post Moment: bottom sheet with camera/gallery picker + text overlay option
- 24hr expiry — show remaining time on own Moment (e.g. Expires in 3h)

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
| UX Review | Iris | pending |
| CSS Review | Cosmo | pending |
