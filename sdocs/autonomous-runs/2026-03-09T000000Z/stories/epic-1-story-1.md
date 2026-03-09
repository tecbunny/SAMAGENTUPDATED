# Story 1.1 — Quick Login & Avatar Creation

**Epic:** Epic 1 — User Onboarding & Identity
**Story ID:** epic-1-story-1
**Status:** pending
**Priority:** High (blocking all other epics)

## User Story
As a new user, I want to sign in via Google/Apple and create a customizable avatar so that I can start chatting without immediately revealing my real face.

## Acceptance Criteria
- [ ] AC1: OAuth integration with Apple Sign-In is functional
- [ ] AC2: OAuth integration with Google Sign-In is functional
- [ ] AC3: Avatar builder UI is presented immediately after sign-in
- [ ] AC4: Avatar supports at minimum: hair style, eye style, clothing colour
- [ ] AC5: Avatar is saved to user profile on completion
- [ ] AC6: User is navigated to interest selection (Story 1.2) upon avatar save
- [ ] AC7: Sign-in flow completes in under 3 seconds on a standard connection

## Technical Notes (Atlas)
- Use passport-apple and passport-google-oauth20 for Node.js OAuth
- Avatar represented as JSON config stored in PostgreSQL users.avatar_config
- Rive-based 2D avatar recommended over full 3D for MVP
- JWT issued on successful OAuth for session management

## UX Notes (Iris)
- Avatar builder must be accessible — colour pickers need contrast validation
- All form inputs require ARIA labels
- Loading spinner required during OAuth redirect
- WCAG 2.1 AA compliance required on all screens

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
| UX Review | Iris | pending |
