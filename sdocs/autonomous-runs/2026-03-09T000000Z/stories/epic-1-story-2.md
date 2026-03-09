# Story 1.2 — The Interest Graph

**Epic:** Epic 1 — User Onboarding & Identity
**Story ID:** epic-1-story-2
**Status:** pending
**Priority:** High (required for matchmaking)

## User Story
As a user, I want to select and rank my top 5 interest tags so that the matchmaking algorithm finds highly compatible chat partners.

## Acceptance Criteria
- [ ] AC1: Searchable tag database is presented during onboarding
- [ ] AC2: User can select a minimum of 1 and maximum of 5 tags
- [ ] AC3: Tags are rankable by drag-and-drop or numbered priority
- [ ] AC4: Selected tags are saved to user profile in PostgreSQL
- [ ] AC5: Tags are displayed on the users public profile page
- [ ] AC6: Tag database contains at minimum 100 seed interest tags

## Technical Notes (Atlas)
- tags table in PostgreSQL with full-text search index
- user_tags join table storing (user_id, tag_id, rank)
- Seeded with minimum 100 tags at migration time
- REST endpoint: PUT /users/:id/tags accepts ordered array

## UX Notes (Iris)
- Search input must show results within 200ms (debounced)
- Selected tags displayed as chips with remove action
- Rank order must be visually clear (numbered or drag handle)
- WCAG 2.1 AA — keyboard navigable tag selection

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
