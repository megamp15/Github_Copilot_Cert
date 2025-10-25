# Code Review with Copilot - Quick Guide

## Quick Start (GitHub.com)

```
1. Open PR
2. Reviewers menu → Select "Copilot"
3. Wait <30 seconds
4. Review comments
5. Apply fixes
```

**Result**: Comment review (not approval/rejection)

## What Copilot Reviews

| Issue Type         | Example                                  |
| ------------------ | ---------------------------------------- |
| **Security**       | Unsafe `eval()`, `exec()`, SQL injection |
| **Type hints**     | Missing function parameter types         |
| **Formatting**     | Inconsistent style, typos                |
| **Bugs**           | Logic errors, edge cases                 |
| **Best practices** | Non-idiomatic patterns                   |

## Copilot Review Characteristics

| Aspect                 | Details                           |
| ---------------------- | --------------------------------- |
| **Speed**              | <30 seconds typically             |
| **Type**               | Comment review only               |
| **Merge blocking**     | Never blocks merges               |
| **Required approvals** | Doesn't count toward requirements |
| **Customization**      | `.github/copilot-instructions.md` |

## Three Levels of Automation

| Level            | Scope          | Who Configures | Plan     |
| ---------------- | -------------- | -------------- | -------- |
| **Account**      | All your PRs   | You            | Pro/Pro+ |
| **Repository**   | Single repo    | Repo admin     | Any      |
| **Organization** | Multiple repos | Org owner      | Any      |

## Setup: Account-Level (Pro/Pro+ Only)

```
1. Profile picture → Your Copilot
2. Find "Automatic Copilot code review"
3. Select "Enabled"
```

**Result**: Auto-added to all your future PRs

## Setup: Repository-Level

```
1. Repo → Settings
2. Rules → Rulesets
3. New ruleset → New branch ruleset
4. Name + set "Active" + target branches
5. Enable "Require PR before merging"
6. Select "Request review from Copilot"
7. Create
```

**Optional**: Enable "Require conversation resolution"

## Setup: Organization-Level

```
1. Profile → Your organizations → Select org
2. Settings → Repository → Rulesets
3. New branch ruleset
4. Name + "Active"
5. Add target repos (use patterns: *service, frontend-*)
6. Define branches
7. Enable PR + Copilot review
8. Create
```

**Repository patterns**:

- `*service` - All repos ending in "service"
- `frontend-*` - All repos starting with "frontend-"
- `*` - All repositories

## Local IDE Reviews (Before PR)

### Setup

Create `.github/copilot-instructions.md`:

```markdown
# Code Review Guidelines

- Focus on security and avoid unsafe string interpolation
- Ensure functions have docstrings
- Flag repetitive code patterns
- Enforce 80-character line limit
```

### IDE Support

| IDE           | Support |
| ------------- | ------- |
| **VS Code**   | ✅ Full |
| **JetBrains** | ✅ Full |

**Benefit**: Catch issues before pushing code

## Path-Specific Instructions

**Location**: `.github/instructions/`

**Format**:

```markdown
---
applyTo: "app/models/**/*.rb"
---

# Security Guidelines

- Use parameterized queries
- Validate all user input
- Sanitize output
```

**Common patterns**:

| Pattern              | Matches            |
| -------------------- | ------------------ |
| `**/*.py`            | All Python files   |
| `src/**/*.ts`        | TypeScript in src/ |
| `app/models/**/*.rb` | Ruby models        |
| `**/*.test.js`       | All test files     |
| `**`                 | All files          |

## Custom Instructions Benefits

| Benefit            | Impact                            |
| ------------------ | --------------------------------- |
| **Consistency**    | Same standards across all reviews |
| **Team alignment** | Copilot follows team rules        |
| **Automated**      | No manual style checking          |

## Review Workflow Comparison

### Traditional

```
PR opened → Wait for human →
Vague comments → Clarification →
Back-and-forth → Approved
Time: Hours to days
```

### With Copilot

```
PR opened → Copilot reviews (<30s) →
Specific comments → Developer fixes →
Human reviews architecture →
Approved
Time: Minutes to hours
```

## PRU Usage in Reviews

| Activity                | PRU Cost             |
| ----------------------- | -------------------- |
| **Large PR (500+)**     | 1-3 PRUs             |
| **Small PR (<100)**     | 0 PRUs (lightweight) |
| **IDE review**          | 1-2 PRUs             |
| **Custom instructions** | +1 PRU               |
| **Security scan**       | 1-3 PRUs             |

## Quick Decision: When to Use

### ✅ Use Copilot Reviews For

- Routine checks
- Style consistency
- Security basics
- Quick feedback
- Multi-language PRs

### ⚠️ Rely on Humans For

- Architectural decisions
- Business logic
- Nuanced trade-offs
- Final approval
- Complex refactoring

## Comment Interaction

**Like teammate comments**:

- React with emoji (👍, 👎, 🎉)
- Mark as resolved
- Reply to comments
- Have discussions

## Apply Fixes Two Ways

### Method 1: Direct Commit

```
Copilot flags issue →
Commit fix from PR interface
```

### Method 2: Ask Copilot

```
Peer comment: "Replace exec() with safer function"

Your prompt:
"Suggest fix for this review comment"

Copilot proposes patch →
Test locally → Commit
```

## Complete Review Pipeline

```
Code pushed →
Copilot review (automatic) →
Status checks (tests, scanning) →
Human review (architecture) →
Merge
```

**Components**:

| Component    | Automated | Purpose       |
| ------------ | --------- | ------------- |
| **Copilot**  | ✅ Yes    | Style, basics |
| **Tests**    | ✅ Yes    | Functionality |
| **Scanning** | ✅ Yes    | Security      |
| **Human**    | ❌ No     | Architecture  |

## Troubleshooting

| Issue                     | Check               | Fix                                   |
| ------------------------- | ------------------- | ------------------------------------- |
| **Not in Reviewers list** | Plan & settings     | Verify Pro/Pro+/Business/Enterprise   |
| **No comments appear**    | Review completion   | Wait 30s, refresh page                |
| **Comments unclear**      | Custom instructions | Add `.github/copilot-instructions.md` |
| **Too many comments**     | Thresholds          | Adjust guidelines                     |

## Quick Reference: Setup Times

| Setup Type              | Time Required           |
| ----------------------- | ----------------------- |
| **Account**             | 30 seconds              |
| **Repository**          | 2-3 minutes             |
| **Organization**        | 5-10 minutes            |
| **Custom instructions** | 10-20 minutes (initial) |

## Best Practices

✅ **Self-review in IDE** before opening PR
✅ **Use custom instructions** for team standards
✅ **Enable conversation resolution** to ensure feedback is read
✅ **Pair with status checks** for comprehensive pipeline
✅ **Track PRU usage** if using automatic reviews
✅ **Start with critical repos** before scaling

## Example Custom Instructions

```markdown
# Security

- Flag eval(), exec(), subprocess without sanitization
- Require input validation

# Style

- 80-character line limit
- Descriptive variable names (no single letters)

# Performance

- Highlight N+1 query patterns
- Flag sync operations that could be async
```

## Module References

📚 [What Copilot Adds to Reviews](../Fundamentals_Part_2/4_Leveling_up_code_reviews_and_pull_requests_with_Github_Copilot.md#what-github-copilot-adds-to-the-review-process)
📚 [Using as Reviewer on GitHub.com](../Fundamentals_Part_2/4_Leveling_up_code_reviews_and_pull_requests_with_Github_Copilot.md#using-copilot-as-a-reviewer-in-githubcom)
📚 [Automating Reviews](../Fundamentals_Part_2/4_Leveling_up_code_reviews_and_pull_requests_with_Github_Copilot.md#catching-issues-early-and-automating-reviews-with-copilot)
