# GitHub Copilot Spaces - Quick Guide

## What is a Space?

Dedicated AI chat with **curated context** (files, issues, PRs, instructions) for **focused, reproducible answers**.

**Chat vs Space**: Chat = broad discovery | Space = deep, consistent answers on specific topic

## When to Use

| ✅ Use Space | ❌ Use Chat Instead |
|-------------|-------------------|
| Runbooks, playbooks, workflows | General exploration |
| Service-specific questions | Wide codebase discovery |
| Repeatable tasks | One-off questions |
| Consistent answers needed | Broad research |

## Quick Start

1. Go to https://github.com/copilot/spaces
2. **Create space** → Name clearly (e.g., "API-Onboarding")
3. Choose owner: Personal or Org
4. Add context (see below)
5. **Save**

## Adding Context

| Type | What to Add | Example |
|------|-------------|---------|
| **Instructions** | Focus, tone, tasks | "Summarize PRs, use formal tone" |
| **Files/Folders** | Repo code, docs | config.yaml, README.md |
| **Issues/PRs** | Paste URLs | github.com/org/repo/issues/123 |
| **Uploads** | Local files | Screenshots, spreadsheets |
| **Text** | Notes, transcripts | Meeting notes, requirements |

**Tip**: Files auto-update from default branch

## Best Practices

### ✅ Do
- One job per Space
- Lead with most important sources (order matters)
- Include 1-3 examples
- Keep questions scoped to sources
- Link version-controlled files
- Review monthly/per release

### ❌ Don't
- Let Space sprawl
- @mention people (won't work)
- Paste sensitive data
- Expect outside content discovery
- Use Copilot extensions (can't invoke)
- Include noisy sources

## Governance Checklist

**Setup**
- [ ] Clear title ("ServiceName-Purpose")
- [ ] Add "How to use" note
- [ ] Set visibility (Personal/Org)
- [ ] Include examples

**Maintenance**
- [ ] Assign owner
- [ ] Review cadence
- [ ] Test 2-3 prompts
- [ ] Prune stale sources

## Example Prompts

```
✅ "Summarize onboarding steps from attached docs"
✅ "Generate SQL query following schema.sql format"
✅ "Create deployment script using config.yaml"
```

## Security

- Inherits GitHub permissions
- Users see only what they can access
- No new access granted
- Use linked files, not pasted secrets

## Sharing

**Personal**: Only you
**Org**: Team members with proper permissions
**Share**: By link or org catalog
