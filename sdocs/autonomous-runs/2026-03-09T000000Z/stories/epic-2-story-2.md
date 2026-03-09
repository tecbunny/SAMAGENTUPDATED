# Story 2.2 — In-Chat Icebreakers

**Epic:** Epic 2 — Core Chat & Matchmaking
**Story ID:** epic-2-story-2
**Status:** pending
**Priority:** Medium

## User Story
As a user, I want the app to suggest conversation starters so that we do not just say "hey" and "how are you."

## Acceptance Criteria
- [ ] AC1: Chat initiates with a system-generated random icebreaker prompt
- [ ] AC2: Icebreaker prompt is visible to both matched users simultaneously
- [ ] AC3: A Shuffle Prompt button allows either user to request a new prompt
- [ ] AC4: At least 50 unique icebreaker prompts exist in the database
- [ ] AC5: Prompt database includes prompts seeded from interest tags when available
- [ ] AC6: Icebreaker prompt display does not block the chat input

## Technical Notes (Atlas)
- icebreakers table in PostgreSQL (id, prompt_text, tags[], created_at)
- On match creation, server selects random prompt weighted by shared tags
- shuffle_prompt Socket.io event — server pushes new prompt to both clients
- Seed with minimum 50 generic and tag-specific prompts

## UX Notes (Iris)
- Prompt displayed as a styled card above the message list
- Shuffle button: icon button inline with prompt card, not blocking input
- Prompt text must be readable — min 16px, sufficient contrast
- Shuffle should animate (fade/slide) to signal change

## TDD Phases
| Phase | Agent | Status |
|-------|-------|--------|
| RED | Titan | pending |
| GREEN | Dyna | pending |
| REFACTOR | Argus | pending |
| UX Review | Iris | pending |
