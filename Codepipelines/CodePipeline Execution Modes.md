# CodePipeline Execution Modes

## SUPERSEDED (Default)

**Behavior:**
New execution cancels in-progress execution and starts immediately

**Use when:**
- Latest code always most important
- Don't need to deploy every commit
- Fast-moving development

**Example:**
Commit A running → Commit B arrives → A cancelled, B starts

## QUEUED

**Behavior:**
New executions wait for current to finish, then run in order

**Use when:**
- Every commit must be deployed
- Order matters
- Can't skip versions

**Example:**
Commit A running → Commit B queued → A finishes → B starts

## PARALLEL

**Behavior:**
Multiple executions run simultaneously

**Use when:**
- Independent deployments
- Testing different branches
- No dependencies between runs

**Example:**
Commit A running → Commit B also starts running

## Comparison

| Mode | Concurrent | Skips Commits | Use Case |
|------|-----------|---------------|----------|
| SUPERSEDED | No | Yes | Latest only matters |
| QUEUED | No | No | Every commit needed |
| PARALLEL | Yes | No | Independent runs |

## Exam Signals

"Latest version always" → SUPERSEDED
"Deploy every commit in order" → QUEUED
"Multiple simultaneous" → PARALLEL
"Don't skip any version" → QUEUED
"Cancel old if new arrives" → SUPERSEDED