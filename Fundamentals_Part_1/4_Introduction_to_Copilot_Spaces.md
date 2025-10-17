# GitHub Copilot Spaces

## What is a Copilot Space?

A dedicated AI chat environment grounded in **curated context** you choose (files, issues, PRs, instructions).

**Key Difference from Chat**: Spaces trade breadth for depth - more consistent, reproducible answers on focused topics.

## When to Use Spaces

| Use Space | Use Regular Chat |
|-----------|-----------------|
| Consistent answers on specific topic | Broad discovery across codebase |
| Runbooks, playbooks, workflows | General exploration |
| Tightly scoped service/component | Wide-ranging questions |
| Repeatable domain-specific tasks | One-off inquiries |

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-spaces/1-introduction)

# Creating Your First Space

**Steps**:
1. Go to https://github.com/copilot/spaces
2. Click **Create space**
3. Name it clearly (e.g., "ServiceName—Onboarding Helper")
4. Choose owner: Personal or Organization
5. Add description (helps discoverability)
6. Click **Save**

## Adding Context

### Two Types

| Type | What | Example |
|------|------|---------|
| **Instructions** | Free text describing focus, tasks | "Summarize onboarding, write formal tone" |
| **Attachments** | Files, issues, PRs, uploads | Code files, markdown docs, config |

### Attachment Options
- **Files/Folders** from GitHub repos
- **Issues/PRs** (paste URLs)
- **Uploads** (local files: images, docs)
- **Text Content** (paste notes, transcripts)

**Note**: GitHub files reference **default branch** (auto-updates as code evolves)

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-spaces/2-create-first-space)

# Sharing, Discoverability, and Governance

## Visibility & Security

- **Personal**: Only you
- **Organization**: Team members (inherits GitHub permissions)
- Users only see content they already have access to
- Share by link or org catalog

## Governance Checklist

**Setup**
- [ ] Clear, purpose-driven title ("one job per Space")
- [ ] 1-2 sentence description
- [ ] "How to use" note in instructions
- [ ] Set owner & visibility
- [ ] Include 1-3 canonical examples

**Maintenance**
- [ ] Assign maintainer
- [ ] Set review cadence (monthly/per release)
- [ ] Test prompts regularly
- [ ] Prune obsolete sources
- [ ] No sensitive data in free text

**Discoverability**
- [ ] Consistent naming conventions
- [ ] Add tags/keywords
- [ ] Announce in org catalog

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-spaces/3-share-discover-govern)

# Do's and Don'ts

## ✅ Do

- Keep questions scoped to attached sources
- Treat Space as focused on single task/domain
- Use Space's terminology for consistency
- Request runnable, verifiable outputs
- Add 1-3 high-quality examples
- Keep context fresh and well-ordered
- Link version-controlled files
- Lead with most important sources (order matters)

## ❌ Don't

- @mention people (won't notify)
- Use Copilot extensions (can't invoke in Spaces)
- Expect Space to discover outside content
- Let Space sprawl beyond single job
- Exceed model context limits
- Paste sensitive data in free text
- Include noisy/irrelevant sources

## Prompting Patterns

```
✅ "Summarize onboarding from attached files"
✅ "Generate deployment script using config.yaml, follow example.sh format"
✅ "SQL query for analytics, reference schema file used"
```

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-spaces/6-working-guide-space)
