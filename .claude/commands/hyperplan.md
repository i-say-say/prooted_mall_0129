---
name: hyperplan
description: Deep interview-based planning with comprehensive requirements gathering
---

# Hyperplan Skill

Activate plan mode with comprehensive deep-dive interviews to gather complete specifications before implementation.

## Activation

When this skill is invoked:

1. **Enter Plan Mode** using `EnterPlanMode` tool
2. **Conduct Deep Interviews** using `AskUserQuestion` tool
3. **Generate Plan Name** automatically based on the topic
4. **Save Final Spec** to `plans/YYYY-MM-DD_{plan-name}.md`

## Usage

```
/hyperplan presigned URL 기반 다중 파일 업로드 구현
/hyperplan 사용자 인증 시스템을 JWT에서 세션 기반으로 변경
/hyperplan 대시보드에 실시간 알림 기능 추가
```

The user provides a description of what they want. Claude:
1. Enters plan mode
2. Conducts deep interviews
3. Generates an appropriate plan name (e.g., `presigned-url-upload`, `auth-jwt-to-session`)
4. Saves to `plans/2024-01-15_presigned-url-upload.md`

## Interview Protocol

### Core Principles

- Questions must NOT be obvious, generic, or superficial
- Each question must probe deeply into one specific aspect
- Continue interviewing until ALL dimensions are fully explored
- Never assume - always ask
- Follow up on vague answers with more specific probes

### Interview Dimensions

Cover ALL of the following areas comprehensively:

#### 1. Technical Implementation
- Architecture decisions (patterns, layers, modules)
- Data flow and state management
- API design and contracts
- Database schema implications
- Integration points with existing code
- Performance considerations (caching, optimization)
- Error handling strategies
- Security implications

#### 2. UI/UX Considerations
- User workflows and journeys
- Loading states and transitions
- Error states and recovery flows
- Edge cases in user interaction
- Accessibility requirements
- Responsive design needs
- Animation and feedback patterns

#### 3. Concerns and Risks
- Technical debt implications
- Breaking changes and migrations
- Dependencies and version conflicts
- Testing complexity
- Deployment considerations
- Rollback strategies
- Monitoring and observability

#### 4. Trade-offs
- Build vs buy decisions
- Performance vs maintainability
- Flexibility vs simplicity
- Short-term vs long-term impact
- Scope reduction options
- Alternative approaches considered

#### 5. Integration Context
- How does this fit with existing features?
- What existing code will be affected?
- What are the boundaries of this change?
- What should explicitly NOT be in scope?

### Interview Flow

1. **Initial Context** (1-2 questions)
   - Clarify the core goal and motivation
   - Understand the user's mental model

2. **Deep Dive** (4-8 questions per dimension)
   - Ask specific, technical questions
   - Probe edge cases and failure modes
   - Explore alternatives and trade-offs

3. **Validation** (1-2 questions)
   - Confirm understanding
   - Identify any gaps

4. **Finalization**
   - Summarize decisions
   - Save to `{plan-name}.md`

## Question Quality Examples

### BAD (Too Generic)
- "What features do you want?"
- "How should it look?"
- "Any concerns?"

### GOOD (Specific and Probing)
- "When a user uploads a file that already exists, should we: (a) reject silently, (b) show conflict UI for user decision, (c) auto-version with suffix, or (d) overwrite?"
- "For the presigned URL TTL, 1 hour is standard, but given your workflow where users might step away mid-upload, should we consider longer TTL with the tradeoff of slightly increased security exposure?"
- "If MSA returns a partial success (3/5 files uploaded), should the UI: (a) show all as failed for retry, (b) show mixed state with individual retry, (c) auto-retry failed ones silently?"

## Output Format

After interviews complete, save to `plans/YYYY-MM-DD_{plan-name}.md`:

```markdown
# Implementation Plan: {Title}

## Overview
[Brief summary of what will be built]

## Decisions Made

### Architecture
[Key architectural decisions with rationale]

### Data Flow
[How data moves through the system]

### API Design
[Endpoints, schemas, contracts]

### UI/UX
[User flows, states, interactions]

### Error Handling
[How errors are handled at each layer]

## Trade-offs Accepted
[Explicit trade-offs and why]

## Out of Scope
[What is explicitly NOT included]

## Implementation Steps
[Ordered list of implementation tasks]

## Verification
[How to verify the implementation is correct]
```

## File Naming

Claude automatically generates a plan name based on the topic:

| User Input | Generated File |
|------------|----------------|
| presigned URL 업로드 구현 | `plans/2024-01-15_presigned-url-upload.md` |
| JWT → 세션 인증 변경 | `plans/2024-01-15_auth-session-migration.md` |
| 실시간 알림 추가 | `plans/2024-01-15_realtime-notifications.md` |

Plan names are kebab-case, concise, and descriptive.
