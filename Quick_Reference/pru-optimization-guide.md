# PRU (Premium Request Units) Optimization Guide

## What Are PRUs?

**PRUs** = Tokens that unlock Copilot's advanced capabilities (deeper analysis, custom instructions, larger diffs)

**Think of it as**: Extra gear for complex tasks

## When PRUs Are Used

| Feature                 | PRU Cost | Trigger                                        |
| ----------------------- | -------- | ---------------------------------------------- |
| **Agent Mode (IDE)**    | 2-5 PRUs | Multi-step workflows                           |
| **Coding Agent**        | 1 PRU    | Per model request                              |
| **PR Review (large)**   | 1-3 PRUs | 500+ line changes                              |
| **IDE deep analysis**   | 1-2 PRUs | Local comprehensive review                     |
| **Custom instructions** | +1 PRU   | When `.github/copilot-instructions.md` applied |

## When PRUs Are NOT Used

| Feature                 | PRU Cost | Use For                     |
| ----------------------- | -------- | --------------------------- |
| **Inline suggestions**  | 0 PRUs   | Code completion as you type |
| **Small refactors**     | 0 PRUs   | Single-line changes         |
| **Simple chat**         | 0 PRUs   | Basic questions             |
| **Code explanations**   | 0 PRUs   | Understanding code          |
| **Lightweight reviews** | 0 PRUs   | Small changes on GitHub.com |

## Decision Matrix: Use PRUs?

| Change Type             | Size         | Risk   | Use PRUs? | Why                  |
| ----------------------- | ------------ | ------ | --------- | -------------------- |
| **Production refactor** | 1,500+ lines | High   | ✅ Yes    | Large, high-risk     |
| **Security code**       | Any          | High   | ✅ Yes    | Security critical    |
| **New feature**         | 500+ lines   | Medium | ✅ Yes    | Significant addition |
| **Documentation**       | Any          | Low    | ❌ No     | Low risk, non-code   |
| **Config change**       | Small        | Low    | ❌ No     | Simple, low impact   |
| **Typo fix**            | 1-2 lines    | Low    | ❌ No     | Trivial              |

## Four Optimization Strategies

### 1. Set Usage Alerts

| Threshold | Action                   | Example                     |
| --------- | ------------------------ | --------------------------- |
| **75%**   | Monitor closely          | Review consumption patterns |
| **90%**   | Prioritize critical only | Defer non-urgent reviews    |
| **100%**  | Emergency protocol       | Upgrade discussion          |

### 2. Use Strategically

**Reserve PRUs for**:

```
✅ Large PRs (500+ lines)
✅ Security-sensitive code
✅ Production features
✅ Multi-file refactors
✅ Complex algorithms
```

**Skip PRUs for**:

```
❌ Documentation updates
❌ Typo fixes
❌ Config tweaks
❌ Comment changes
❌ Small bug fixes (<50 lines)
```

### 3. Refine Prompts

**Poor prompts waste PRUs**:

| Quality     | Example                                     | PRUs Used | Retries |
| ----------- | ------------------------------------------- | --------- | ------- |
| ❌ **Poor** | "Review this"                               | 3-4       | 2-3     |
| ⚠️ **Okay** | "Check for security"                        | 2         | 1       |
| ✅ **Good** | "Review for SQL injection in database code" | 1         | 0       |

**Prompt tips**:

- Be specific about what to check
- Reference relevant files
- Mention guidelines
- State expected output
- Include context

### 4. Scale Up If Needed

**Signals to upgrade**:

- Hit 100% PRUs every month
- Can't review important PRs
- Team growing rapidly
- Quality metrics declining

## Quick PRU Budget Estimation

```
Team size × PRs per dev per month = Total PRs
Large PRs (40%) × PRU per review (2) = Monthly PRUs needed

Example:
10 devs × 8 PRs/month = 80 PRs total
80 PRs × 40% large = 32 large PRs
32 large PRs × 2 PRUs = 64 PRUs/month
```

## PRU Consumption by Feature

### Agent Mode (IDE)

```
Draft-review workflow: 2-3 PRUs
Premium reasoning: 4+ PRUs
Standard workflow: 2 PRUs
```

### Coding Agent (GitHub)

```
Simple task: 1-3 PRUs
Complex task: 5-10 PRUs
Multi-step iteration: 10+ PRUs
```

### Code Reviews

```
Small PR (<100 lines): 0 PRUs (lightweight)
Medium PR (100-500): 1 PRU
Large PR (500+): 1-3 PRUs
With custom instructions: +1 PRU
```

## Measuring PRU Impact

### Three Key Metrics

| Metric                   | What to Track           | Target           |
| ------------------------ | ----------------------- | ---------------- |
| **PR lead time**         | Days from open to merge | 50-70% reduction |
| **Quality indicators**   | Post-merge issues       | 80% reduction    |
| **Developer experience** | Team satisfaction       | High approval    |

### Example ROI Calculation

```
Before Copilot:
- Review time: 2 hours/PR
- PRs per week: 20
- Weekly hours: 40 hours

After Copilot + PRUs:
- Review time: 30 min/PR
- PRs per week: 20
- Weekly hours: 10 hours
- PRU cost: ~$50/month

Savings: 30 hours/week @ $100/hr = $3,000/month
ROI: 60x return on investment
```

## Common PRU Waste Scenarios

| Waste Source          | % of PRUs | Solution                |
| --------------------- | --------- | ----------------------- |
| **Documentation PRs** | 25%       | Use lightweight reviews |
| **Vague prompts**     | 15%       | Refine to be specific   |
| **Retries**           | 10%       | Better initial prompts  |
| **Config changes**    | 5%        | Skip PRU reviews        |

## Quick Optimization Checklist

**Before requesting PRU-powered review**:

- [ ] Is this 500+ lines or security-sensitive?
- [ ] Is the prompt specific and clear?
- [ ] Have I checked PRU budget status?
- [ ] Could this use lightweight review instead?
- [ ] Is this production-impacting?

**If NO to first or last question → Skip PRUs**

## Plan Comparison

| Plan           | PRUs/Month | Best For        |
| -------------- | ---------- | --------------- |
| **Pro**        | Base       | Individual devs |
| **Pro+**       | Enhanced   | Power users     |
| **Business**   | Scaled     | Teams           |
| **Enterprise** | Custom     | Large orgs      |

## Emergency PRU Management

**When you hit 90% of budget**:

```
1. Pause automatic reviews (except critical repos)
2. Audit recent PRU usage
3. Identify waste sources
4. Implement quick wins:
   - Skip docs reviews
   - Refine prompts
   - Prioritize production code
5. Prepare upgrade justification if needed
```

## Best Practices Summary

✅ **Strategic**: Reserve for large, high-risk changes
✅ **Alert-driven**: Set thresholds at 75%, 90%, 100%
✅ **Prompt quality**: Specific requests reduce waste
✅ **Track metrics**: Monitor lead time and quality
✅ **Regular audits**: Monthly consumption reviews
✅ **Scale appropriately**: Upgrade when consistently maxed

## Module Reference

📚 [Full Guide: Measuring Impact and Optimizing PRUs](../Fundamentals_Part_2/4_Leveling_up_code_reviews_and_pull_requests_with_Github_Copilot.md#measuring-impact-and-optimizing-premium-request-units-prus)
