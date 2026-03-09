# Story 4.2 — AI Content Moderation

**Epic:** Epic 4 — Privacy, Safety and Moderation
**Story ID:** epic-4-story-2
**Status:** pending
**Priority:** Critical (safety — launch blocker)

## User Story
As the platform admin, I want an AI filter to blur unsolicited explicit images and mask severe hate speech automatically so that users are not exposed to harmful content.

## Acceptance Criteria
- [ ] AC1: Images sent in chat are scanned for NSFW content before display
- [ ] AC2: Detected NSFW images are blurred with an Explicit Content Warning overlay
- [ ] AC3: User can tap the overlay to reveal image (opt-in consent)
- [ ] AC4: Severe hate speech text is masked with asterisks on receive
- [ ] AC5: A blacklist of severe slurs/hate terms is maintained and enforced
- [ ] AC6: Moderation is asynchronous — message shown with blur/mask; original stored for review
- [ ] AC7: Moderation decisions are logged for admin audit trail
- [ ] AC8: False-positive rate target less than 5% (tuneable threshold)

## Technical Notes (Atlas)
- Image moderation: AWS Rekognition DetectModerationLabels API (async, post-upload)
- Text moderation: server-side regex and ML classifier against blacklist
- Async flow: image stored in S3 then message sent with moderation_status: pending then Rekognition callback then update to safe or blurred
- moderation_log table: (id, content_type, content_ref, result, confidence, actioned_at)

## UX Notes (Iris)
- Blur overlay: frosted glass effect, warning icon, tap-to-reveal affordance
- Masked text: visible asterisk pattern — user understands content was filtered
- No jarring flash or layout shift when moderation result arrives

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
