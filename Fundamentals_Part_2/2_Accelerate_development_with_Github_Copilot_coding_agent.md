# Understanding and enabling the GitHub Copilot coding agent

## What is the GitHub Copilot Coding Agent?

**Coding Agent** = Autonomous development assistant that runs **inside GitHub itself** (not just your IDE). Acts like a background teammate.

### How It Works

**You give it a scoped task** → Agent handles everything:

1. Creates a branch
2. Writes commits
3. Opens draft pull request
4. Updates PR description with status
5. Requests your review

**Task examples**: Bug fix, incremental feature, documentation update

## Availability & Plans

| Category         | Details                                                                                                   |
| ---------------- | --------------------------------------------------------------------------------------------------------- |
| **Plans**        | Pro, Pro+, Business, Enterprise                                                                           |
| **Repositories** | All GitHub-hosted repos (except managed user accounts or where explicitly disabled)                       |
| **Access**       | GitHub.com, GitHub Mobile, API/CLI, Agents panel, Copilot Chat, IDE, MCP-supported tools, Raycast (macOS) |

## What the Coding Agent Can Do

| Task               | Description                                   |
| ------------------ | --------------------------------------------- |
| **Fix bugs**       | Debug and resolve bugs/regressions            |
| **New features**   | Implement incremental features                |
| **Test coverage**  | Improve coverage or generate missing tests    |
| **Documentation**  | Update or create documentation                |
| **Technical debt** | Address debt and "nice-to-have" backlog items |

## Delegating Work to the Agent (2 Ways)

### Method 1: Assign an Issue to Copilot

**Where**: GitHub.com, GitHub Mobile, API, CLI

**How**: Assign issue → Agent works → Opens PR → Requests review

### Method 2: Ask Copilot to Create a PR

**Where**:

- Agents panel on GitHub
- Copilot Chat
- Your IDE
- Other agentic tools with MCP support
- Raycast on macOS

**Iteration**: Mention `@copilot` in PR comment to ask it to iterate on work

## Coding Agent vs Traditional IDE Assistants

| Aspect            | Traditional IDE Assistant                    | Coding Agent                          |
| ----------------- | -------------------------------------------- | ------------------------------------- |
| **Location**      | Works locally in IDE                         | Runs on GitHub                        |
| **Manual work**   | You create branches, push commits, write PRs | Agent automates all of this           |
| **Visibility**    | Private session, team can't see              | All work visible as commits on GitHub |
| **Traceability**  | Limited                                      | Full session logs & PR history        |
| **Steering**      | Synchronous local sessions                   | Via PR review comments                |
| **Collaboration** | Individual work                              | Teammates can see steps & jump in     |

**Key Difference**: Traditional = local help → Coding Agent = transparent, collaborative teammate on GitHub

## Coding Agent vs "Agent Mode" in IDEs

⚠️ **Important distinction** - These are different things:

| Feature           | Coding Agent                             | Agent Mode (Copilot Edits)      |
| ----------------- | ---------------------------------------- | ------------------------------- |
| **Where it runs** | GitHub Actions-powered environment       | Your IDE session                |
| **What it does**  | Completes tasks assigned via issues/chat | Performs autonomous local edits |
| **Output**        | Creates pull requests                    | Direct edits in your IDE        |
| **Assignment**    | Via GitHub issues or Copilot Chat        | Within IDE session              |
| **Covered in**    | This module                              | Visual Studio/VS Code feature   |

## Enabling the Coding Agent

### Organization-Owned Repositories

Managed by **organization or enterprise administrators**

### Personal Repositories

Configure in **account settings**

### Before You Start

✅ Ensure agent is enabled before assigning tasks

## Usage Costs: GitHub Actions + PRUs

The coding agent uses **two main resources**:

| Resource                         | What It's For                                      | Cost Model                                      |
| -------------------------------- | -------------------------------------------------- | ----------------------------------------------- |
| **GitHub Actions minutes**       | Ephemeral build/test environment where agent works | Uses your monthly Actions allowance             |
| **Premium Request Units (PRUs)** | Power advanced model reasoning                     | 1 PRU per model request (starting June 4, 2025) |

### PRU & Actions Cost Details

📅 **Starting June 4, 2025**: Agent uses **1 PRU per model request**

✅ **Within monthly allowance**: No extra charges for Actions minutes or PRUs

⚠️ **Beyond allowance**: Additional charges apply

### PRU Usage Best Practices

💡 **Use PRUs where they add value**:

- Multi-file edits
- Test generation
- Broader diffs needing deeper reasoning

⚡ **Save PRUs on**:

- Lightweight edits
- Simple, single-file changes

## Cost Management Summary

| Aspect                 | Strategy                                      |
| ---------------------- | --------------------------------------------- |
| **Budget tracking**    | Monitor Actions minutes & PRU consumption     |
| **Optimize usage**     | Use for complex tasks, avoid for simple edits |
| **Stay within limits** | Use monthly allowances effectively            |
| **Plan ahead**         | Understand costs before assigning work        |

## Key Differences Summary

| vs Traditional IDE Assistant   | vs Agent Mode (IDE)                     |
| ------------------------------ | --------------------------------------- |
| ✅ Works on GitHub (not local) | ✅ Different location (GitHub vs IDE)   |
| ✅ Automates branch/commit/PR  | ✅ Different output (PR vs local edits) |
| ✅ Team-visible & traceable    | ✅ Different assignment method          |
| ✅ Collaborative workflow      | ✅ Different use case                   |

## Next Steps

With agent enabled and costs understood:

1. ✅ Review security posture
2. ✅ Understand risks
3. ✅ Account for limitations
4. ✅ Plan real work assignments

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/1-understand-enable-github-copilot-code-agent)

# Security, risks, and limitations of the Copilot coding agent

## Security Model & Built-In Protections

🔒 **Security is foundational** - Agent respects existing controls + adds its own guardrails

| Protection                     | What It Means                                                                                   |
| ------------------------------ | ----------------------------------------------------------------------------------------------- |
| **Subject to governance**      | Org/enterprise settings govern availability; all your security policies apply                   |
| **Restricted environment**     | Runs in sandbox on GitHub Actions with firewalled internet + read-only repo access              |
| **Branch limits**              | Can only create/push to `copilot/` branches; all branch protections still apply                 |
| **Permission-aware**           | Only responds to users with write permission; ignores comments from others                      |
| **Outside-collaborator rules** | Draft PRs require approval by write-permission user before Actions run; requestor can't approve |
| **Compliance & attribution**   | All commits coauthored with developer who assigned task; clear attribution                      |

**Key Principle**: Agent operates **inside your existing guardrails** + adds extra protections

## Risks & Mitigations

Although built with security in mind, there are risks to plan for. GitHub applies mitigations:

### Risk 1: Agent Pushes Code

**The Risk**: Autonomous code pushes could be dangerous

**Mitigations Applied**:

| Mitigation                  | How It Works                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------- |
| **Write access only**       | Only users with write access can trigger agent work                                               |
| **Branch restrictions**     | Pushes restricted to `copilot/` branches only (not main/master)                                   |
| **Limited credentials**     | Agent's credentials allow simple push only (no direct `git push`)                                 |
| **Workflow approval**       | GitHub Actions workflows won't run until write-permission user clicks "Approve and run workflows" |
| **Requestor can't approve** | Person who requested PR can't approve it, maintaining required approvals                          |

### Risk 2: Access to Sensitive Information

**The Risk**: Agent might access sensitive data

**Mitigation Applied**:

| Mitigation                       | Details                                                   |
| -------------------------------- | --------------------------------------------------------- |
| **Firewall-restricted internet** | Agent's internet access is firewall-restricted by default |
| **Customizable**                 | You can customize or disable the firewall per policy      |

### Risk 3: Prompt Injection

**The Risk**: Malicious hidden instructions in comments/issues

**Mitigation Applied**:

| Mitigation                     | How It Works                                                               |
| ------------------------------ | -------------------------------------------------------------------------- |
| **Hidden character filtering** | HTML comments and hidden characters filtered before passing input to agent |
| **Reduces injection risk**     | Minimizes chance of hidden harmful instructions                            |

⚠️ **Important**: Still review outputs carefully, just as you would code written by any team member

## Known Limitations

Understanding limitations helps you plan usage effectively.

### Workflow Limitations

| Limitation                    | Impact                                                      | Workaround                                             |
| ----------------------------- | ----------------------------------------------------------- | ------------------------------------------------------ |
| **Same repository only**      | Can only make changes in the same repo as assigned issue/PR | Split work across repos if needed                      |
| **Repository-scoped context** | Context limited to assigned repo by default                 | Broaden via MCP if needed                              |
| **One PR per task**           | Opens exactly one pull request per task                     | Break large work into multiple tasks                   |
| **Can't modify existing PRs** | Can't modify PRs it didn't create                           | Add as reviewer for feedback (use Copilot code review) |

### Compatibility Limitations

| Limitation                          | Impact                                                          | What You Need to Know                                                    |
| ----------------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **No commit signing**               | Doesn't sign commits                                            | Must rewrite commit history before merging if you require signed commits |
| **GitHub-hosted runners only**      | Requires GitHub-hosted Ubuntu x64 runners                       | Self-hosted runners not supported                                        |
| **Not for managed user accounts**   | Not available for personal repos owned by managed user accounts | Runners unavailable for these accounts                                   |
| **Ignores content exclusions**      | Agent can see and update excluded files                         | Be aware of this when excluding sensitive files                          |
| **Public code policy not enforced** | "Suggestions matching public code" policy isn't enforced        | References may not be provided                                           |
| **GitHub-hosted repos only**        | Works only with GitHub-hosted repositories                      | Can't use with external repo hosting                                     |
| **No model selection**              | Can't change AI model used by agent                             | Model selected by GitHub                                                 |

## Security & Limitation Summary

### ✅ Security Strengths

- Operates within your existing guardrails
- Sandboxed environment with restricted access
- Permission-aware (write access required)
- Clear attribution via coauthored commits
- Filtered input to prevent prompt injection
- Branch protections still apply

### ⚠️ Key Risks to Manage

- Review code outputs carefully (as with any team member)
- Understand branch restrictions (`copilot/` only)
- Plan for workflow approval requirements
- Be aware of content exclusion limitations

### 📋 Planning Checklist

Before using the coding agent:

- [ ] Understand security model and protections
- [ ] Review risk mitigations
- [ ] Check compatibility with your setup (signed commits? self-hosted runners?)
- [ ] Plan for workflow limitations (one repo, one PR per task)
- [ ] Set expectations for content exclusions behavior
- [ ] Ensure proper permissions configured

## Best Practices

| Practice                   | Why                                                   |
| -------------------------- | ----------------------------------------------------- |
| **Review all agent PRs**   | Treat as code from any team member                    |
| **Use branch protections** | Leverage existing protections for `copilot/` branches |
| **Monitor permissions**    | Ensure only appropriate users have write access       |
| **Plan task scope**        | Work within one-repo, one-PR-per-task constraints     |
| **Document requirements**  | If you need signed commits, plan rewrite process      |

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/2-security-risks-limitations-copilot-code-agent)

# Assigning, tracking, and troubleshooting Copilot coding agent tasks

## How Assignment Works

When you assign an issue to Copilot:

| Step | What Happens             | Visual Signal                                   |
| ---- | ------------------------ | ----------------------------------------------- |
| 1    | Agent acknowledges       | 👀 reaction added to issue                      |
| 2    | Creates dedicated branch | `copilot/` branch created                       |
| 3    | Opens draft PR           | Draft PR linked to issue                        |
| 4    | Begins agent session     | GitHub Actions-powered environment              |
| 5    | Works on task            | Pushes commits + updates PR body with status    |
| 6    | Completes                | Posts "Copilot finished work" + requests review |

⚠️ **Important**: Copilot receives issue title, description, and existing comments **at time of assignment**. Later comments on the issue are **not seen** - add new info as comments on the agent's PR.

## Assigning Issues to Copilot (4 Methods)

### Method 1: GitHub.com

**Steps**:

1. Navigate to repository's **Issues** tab
2. Open issue you want to delegate
3. Right sidebar → **Assignees** → Select **Copilot**

**Also works from**:

- List of issues on repository's Issues page
- GitHub Projects

### Method 2: GitHub Mobile

Assign Copilot directly from mobile app (same as assigning any user)

### Method 3: GitHub CLI

```bash
gh issue edit [issue-number] --add-assignee copilot
```

### Method 4: GraphQL API

Programmatic assignment for automated workflows:

**Step 1: Check availability**

```graphql
query {
  repository(owner: "octo-org", name: "octo-repo") {
    suggestedActors(capabilities: [CAN_BE_ASSIGNED], first: 100) {
      nodes {
        login
        __typename
        ... on Bot {
          id
        }
        ... on User {
          id
        }
      }
    }
  }
}
```

**Step 2: Get repository ID**

```graphql
query {
  repository(owner: "octo-org", name: "octo-repo") {
    id
  }
}
```

**Step 3a: Create and assign new issue**

```graphql
mutation {
  createIssue(
    input: {
      repositoryId: "REPOSITORY_ID"
      title: "Implement comprehensive unit tests"
      body: "DETAILS"
      assigneeIds: ["BOT_ID"]
    }
  ) {
    issue {
      id
      title
      assignees(first: 10) {
        nodes {
          login
        }
      }
    }
  }
}
```

**Step 3b: Assign existing issue**

```graphql
# Get issue ID first
query {
  repository(owner: "monalisa", name: "octocat") {
    issue(number: 9000) {
      id
      title
    }
  }
}

# Then assign
mutation {
  replaceActorsForAssignable(
    input: { assignableId: "ISSUE_ID", actorIds: ["BOT_ID"] }
  ) {
    assignable {
      ... on Issue {
        id
        title
        assignees(first: 10) {
          nodes {
            login
          }
        }
      }
    }
  }
}
```

**Use case**: Integrating Copilot into automated workflows

## Tracking Copilot's Progress (5 Stages)

| Stage                 | Event              | What You See                                    | Timing                       |
| --------------------- | ------------------ | ----------------------------------------------- | ---------------------------- |
| **1. Confirmation**   | Issue acknowledged | 👀 reaction on issue                            | Immediately after assignment |
| **2. PR Creation**    | Draft PR opened    | Draft PR linked to issue, timeline event        | Within seconds               |
| **3. Active Session** | Work begins        | "Copilot started work" in PR timeline           | Shortly after PR creation    |
| **4. Live Updates**   | Ongoing work       | Status messages in PR body, commits pushed      | During session               |
| **5. Completion**     | Work finished      | "Copilot finished work" event, review requested | When task complete           |

### Live Session Logs

**Where**: Agents page (all sessions - past and present visible)

**How to access**: Click **View session** on PR to open live log viewer

**Features**:

- Watch Copilot's actions in real time
- See what it's doing at each step
- Stop session if needed (click **Stop session**)

## Iterating with Copilot

**How to request changes**: Mention `@copilot` in a PR comment

**Workflow**:

1. You leave comment with `@copilot` mention
2. Copilot posts 👀 reaction (confirms receipt)
3. "Copilot started work" appears in PR timeline
4. Copilot resumes work with your feedback

⚠️ **Permission required**: Only comments from users with **write permission** are processed

**Benefit**: Iterate without leaving normal review workflow

## Approvals & Workflows

| Aspect                | Rule                                             | Why                                                            |
| --------------------- | ------------------------------------------------ | -------------------------------------------------------------- |
| **PR state**          | Always draft                                     | Requires human approval before merge                           |
| **GitHub Actions**    | Don't run automatically                          | Security protection                                            |
| **Running workflows** | Click "Approve and run workflows" in merge box   | Manual approval required                                       |
| **PR approval**       | Developer who requested PR **cannot approve it** | Preserves "required reviews" rules, ensures independent review |

**Key takeaway**: Human oversight built into every step

## Troubleshooting Playbook

| Problem                                | Likely Cause                               | Solution                                                                                                                                     |
| -------------------------------------- | ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Copilot not in "Assignees" list**    | Plan eligibility or disabled               | • Verify plan (Pro, Pro+, Business, Enterprise)<br>• Check not disabled at org/repo level<br>• Visit: `github.com/settings/copilot/features` |
| **EMU personal repos**                 | Not available for Enterprise Managed Users | Use organization-owned repositories (requires GitHub-hosted runners)                                                                         |
| **"Cannot create PR" from Chat**       | Agent not available or wrong mention       | • Ensure agent available<br>• In IDEs: mention `@github` (not needed on GitHub.com)                                                          |
| **Assigned but nothing happened**      | Need to refresh                            | Refresh page, look for 👀 reaction, then draft PR                                                                                            |
| **PR created, no progress**            | Session not started                        | • Check PR timeline for "Copilot started work"<br>• Open View session logs                                                                   |
| **Agent not responding to PR comment** | Permission or mention issue                | • Confirm you have write access<br>• Verify mentioned `@copilot` on agent's PR                                                               |
| **Appears stuck**                      | May recover or timeout                     | • Wait (may recover automatically)<br>• Sessions timeout after 1 hour<br>• Retry: unassign/reassign issue or repost comment                  |
| **Actions aren't running**             | Need manual approval                       | Click "Approve and run workflows" in merge box                                                                                               |
| **Pushes don't pass CI**               | Agent needs guidance                       | Provide clear repo-level guidance via `.github/copilot-instructions.md` for self-validation with tests/linters                               |
| **Firewall warnings**                  | Internet restricted by default             | Warnings list blocked address/command<br>Adjust per customization docs                                                                       |
| **Images not picked up**               | Size limit exceeded                        | Max image size: 3.00 MiB (larger images removed)                                                                                             |

## Quick Reference: Assignment Methods

| Method            | When to Use                                   | Complexity      |
| ----------------- | --------------------------------------------- | --------------- |
| **GitHub.com**    | Manual, one-off assignments                   | ⚡ Easy         |
| **GitHub Mobile** | On-the-go assignments                         | ⚡ Easy         |
| **GitHub CLI**    | Command-line workflows                        | ⚡⚡ Moderate   |
| **GraphQL API**   | Automated workflows, programmatic integration | ⚡⚡⚡ Advanced |

## Workflow Summary

```
Assign Issue → 👀 Reaction → Draft PR → Copilot Starts Work →
Regular Updates → Copilot Finished → Review Requested →
Iterate with @copilot → Approve & Merge
```

## Best Practices

| Practice                         | Why                                                  |
| -------------------------------- | ---------------------------------------------------- |
| **Clear issue descriptions**     | Copilot only sees info at assignment time            |
| **Use PR comments for updates**  | Later issue comments aren't seen by agent            |
| **Monitor session logs**         | Track progress in real time                          |
| **Provide repo guidance**        | Use `.github/copilot-instructions.md` for CI/testing |
| **Review before merging**        | Always treat as code from any contributor            |
| **Use write permissions wisely** | Only authorized users should interact                |

## Key Takeaways

✅ **Multiple assignment methods**: GitHub.com, Mobile, CLI, API
✅ **Visible progress tracking**: 5 stages with clear signals (👀, draft PR, timeline events)
✅ **Iterate like with humans**: Use PR comments with `@copilot` mentions
✅ **Built-in safety**: Draft state, approval required, independent review
✅ **Rich troubleshooting**: Clear playbook for common issues

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/3-assign-track-troubleshoot-copilot-code-agent-tasks)

# Customizing, extending and validating the copilot coding agent

## Overview

The coding agent runs in a secure, ephemeral GitHub Actions environment. You can customize it to:

- **Preseed environment** - Preinstall tools, dependencies, secrets
- **Extend capabilities** - Add external tools via Model Context Protocol (MCP)
- **Validate output** - Apply best practices for testing before merge

## Preseeding the Development Environment

### Setup Workflow: `copilot-setup-steps.yml`

**Location**: `.github/workflows/copilot-setup-steps.yml` (on default branch)

**Purpose**: Preinstall dependencies and tools to improve reliability and speed

#### Configuration Requirements

| Requirement           | Details                                                                    |
| --------------------- | -------------------------------------------------------------------------- |
| **Job name**          | Must be named `copilot-setup-steps`                                        |
| **Allowed keys**      | `steps`, `permissions`, `runs-on`, `container`, `services`, `snapshot`     |
| **Timeout**           | `timeout-minutes` ≤ 59                                                     |
| **Checkout depth**    | `actions/checkout` fetch-depth overridden for safe rollback                |
| **Execution**         | Runs standalone for validation, then automatically before agent starts     |
| **Supported runners** | Ubuntu x64 only (self-hosted runners NOT supported)                        |
| **Larger runners**    | Set `runs-on` to label/group (e.g., `ubuntu-4-core`) - must add them first |

#### Example: TypeScript Project

```yaml
name: "Copilot Setup Steps"

on:
  workflow_dispatch:
  push:
    paths:
      - .github/workflows/copilot-setup-steps.yml
  pull_request:
    paths:
      - .github/workflows/copilot-setup-steps.yml

jobs:
  copilot-setup-steps:
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - name: Checkout code
        uses: actions/checkout@v5
      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: "20"
          cache: "npm"
      - name: Install JavaScript dependencies
        run: npm ci
```

#### Git LFS Support

If using Git Large File Storage:

```yaml
jobs:
  copilot-setup-steps:
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - uses: actions/checkout@v5
        with:
          lfs: true
```

#### Firewall Customization

| Default                            | Customization Option                    |
| ---------------------------------- | --------------------------------------- |
| Internet access limited by default | Can customize or disable per org policy |
| Reduces exfiltration risk          | Adjust based on security requirements   |

## Extending with Model Context Protocol (MCP)

### What is MCP?

**MCP** = Open standard for connecting LLMs to **tools** and **data**

**Agent capability**: Use tools from local or remote MCP servers to expand functionality

⚠️ **Limitations**:

- Only **MCP tools** supported (not resources or prompts)
- Remote MCP servers requiring OAuth NOT supported

### Default MCP Servers

| Server                    | Capabilities                         | Token Scope                                       |
| ------------------------- | ------------------------------------ | ------------------------------------------------- |
| **GitHub MCP Server**     | Access issues, PRs, GitHub data      | Read-only, scoped to current repo (customizable)  |
| **Playwright MCP Server** | Read, interact, screenshot web pages | Pages accessible in agent environment (localhost) |

### Repository Configuration

**How to configure**: Admins declare MCP servers via JSON configuration in repo

**Behavior**: Once configured, agent **autonomously uses tools** (no per-use approval prompts)

📚 **See**: [Extending GitHub Copilot coding agent with MCP](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/4-customize-extend-validate-copilot-code-agent)

### MCP Best Practices

| Practice                           | Why                                           |
| ---------------------------------- | --------------------------------------------- |
| **Review third-party MCP servers** | Performance and output quality implications   |
| **Prefer read tools**              | Minimize risk; allow write only when needed   |
| **Validate MCP config carefully**  | Ensure security and correctness before saving |

## Testing & Validating Agent Output

### Accountability & Responsibility

⚠️ **You remain accountable** for quality and security of agent-generated code

### Validation Workflow Checklist

| Step                            | How to Implement                                                                        | Purpose                                     |
| ------------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------- |
| **1. Run CI on every PR**       | Tests, linters, scanning                                                                | Automated quality checks                    |
| **2. Manual approval required** | Click "Approve and run workflows"                                                       | Human gate before automation runs           |
| **3. Manual inspection**        | Review high-impact or sensitive areas                                                   | Catch issues automation might miss          |
| **4. Agent-generated tests**    | Ask agent: "Add Jest unit tests for all functions in `src/utils/` following repo style" | Multi-file test generation (uses PRUs)      |
| **5. Enforce rulesets**         | Configure branch protection rules                                                       | PRs must pass tests + scanning before merge |
| **6. Label agent PRs**          | Use labels like `agent-refactor`, `agent-tests`                                         | Monitor, triage, and revert if needed       |
| **7. Iterate instructions**     | Update `.github/copilot-instructions.md`                                                | Fix repeated mistakes                       |
| **8. Quick reversion**          | Revert and request new changes                                                          | Fast recovery from bad outputs              |

### CI/CD Integration

**Workflow**:

```
Agent creates PR → Draft state → You click "Approve and run workflows" →
CI runs (tests, linters, scanning) → Review results → Manual inspection →
Approve or request changes → Merge
```

### Using PRUs Intentionally for Validation

**When to use PRUs for validation**:

| Task                        | PRU Value | When to Apply           |
| --------------------------- | --------- | ----------------------- |
| **Test coverage expansion** | High      | Critical code paths     |
| **Directory audits**        | High      | Major refactors         |
| **Risky area scans**        | High      | Security-sensitive code |
| **Lightweight checks**      | Low       | Routine changes         |

**Strategy**: Apply PRUs intentionally to maximize value

### Quality Assurance Best Practices

**Ask agent to generate tests**:

```
Example: "Add Jest unit tests for all functions in src/utils/ following repo style"
```

⚠️ **Note**: Multi-file test generation consumes PRUs

**Enforce quality gates**:

- Tests must pass
- Linters must pass
- Security scanning must pass
- Manual review required

### Labeling Strategy

| Label            | Purpose                    | Benefit                  |
| ---------------- | -------------------------- | ------------------------ |
| `agent-refactor` | Tracks refactoring work    | Easy to monitor/revert   |
| `agent-tests`    | Tracks test generation     | Audit test quality       |
| `agent-docs`     | Tracks documentation       | Review doc accuracy      |
| `agent-feature`  | Tracks feature development | Measure agent capability |

### Iterative Improvement

**When you see repeated mistakes**:

1. Update `.github/copilot-instructions.md`
2. Provide clearer guidance for CI/testing
3. Add examples of expected behavior
4. Specify project conventions

**Fast recovery**:

- Revert quickly if output is problematic
- Request new changes from agent with updated instructions
- Learn from mistakes to improve instructions

## Configuration Files Summary

| File                                        | Purpose                               | Required |
| ------------------------------------------- | ------------------------------------- | -------- |
| `.github/workflows/copilot-setup-steps.yml` | Preseed environment with dependencies | Optional |
| `.github/copilot-instructions.md`           | Provide repo-level guidance to agent  | Optional |
| MCP configuration JSON                      | Extend agent with external tools      | Optional |

## Security Considerations

| Aspect                    | Consideration                           | Best Practice                           |
| ------------------------- | --------------------------------------- | --------------------------------------- |
| **Preseeded environment** | Dependencies could have vulnerabilities | Use pinned versions, audit dependencies |
| **MCP extensions**        | Third-party tools add risk              | Review thoroughly, prefer read-only     |
| **Agent PRs**             | Generated code may have issues          | Always run CI, manual inspection        |
| **Firewall**              | Default restricted internet access      | Customize carefully per policy          |

## PRU Optimization for Validation

**High-value PRU usage**:

✅ Comprehensive test generation for critical features
✅ Security audits across multiple files
✅ Performance analysis of complex algorithms
✅ Cross-system impact analysis

**Low-value PRU usage**:

❌ Lightweight syntax checks
❌ Simple single-file edits
❌ Routine documentation updates

**Strategy**: Reserve PRUs for complex validation tasks that benefit from deeper reasoning

## Workflow Integration Example

**Complete validation workflow**:

```
1. Agent assigned issue
2. Agent creates PR (draft)
3. Setup workflow runs (copilot-setup-steps.yml)
4. Agent generates code
5. Agent generates tests
6. You click "Approve and run workflows"
7. CI runs (tests, linters, scanning)
8. You review code manually
9. Check labels (agent-refactor, etc.)
10. Iterate with @copilot if needed
11. Approve and merge
```

## Key Takeaways

✅ **Preseed environment**: Use `copilot-setup-steps.yml` to install dependencies (improves speed/reliability)
✅ **Extend capabilities**: MCP adds external tools (GitHub data, web interaction)
✅ **Validate rigorously**: CI + manual inspection + tests + linting before merge
✅ **Label & track**: Use labels to monitor, triage, and revert agent PRs
✅ **Iterate instructions**: Update `.github/copilot-instructions.md` to fix repeated issues
✅ **PRU strategy**: Use PRUs intentionally for complex validation tasks
⚠️ **You're accountable**: Human oversight required for quality and security

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/4-customize-extend-validate-copilot-code-agent)

# Responsible use of GitHub Copilot coding agent on GitHub.com

## Overview

Learn to use the coding agent responsibly by understanding its purposes, capabilities, and limitations.

**By the end of this section**:

- Understand purpose, capabilities, and limits
- Apply responsible-use practices (scoping, securing, validating)
- Recognize security measures, risks, mitigations, and performance improvements

## About Copilot Coding Agent on GitHub.com

**What it is**: Autonomous and asynchronous software development agent integrated into GitHub

### Core Capabilities

| Capability           | What It Does                                                     |
| -------------------- | ---------------------------------------------------------------- |
| **Task pickup**      | Picks up tasks from issues or Copilot Chat                       |
| **PR creation**      | Creates pull requests automatically                              |
| **Iteration**        | Iterates on PRs in response to comments                          |
| **Tailored changes** | Generates changes based on description and configurations        |
| **Development env**  | Ephemeral environment to make changes, run tests, run linters    |
| **Multi-language**   | Evaluated across various programming languages (English primary) |

### What the Agent Can Do

| Task Type                | Examples                                         |
| ------------------------ | ------------------------------------------------ |
| **Bug fixes**            | Resolve defects and regressions                  |
| **Incremental features** | Implement new features step-by-step              |
| **Prototyping**          | Rapid proof-of-concept development               |
| **Documentation**        | Create and update documentation                  |
| **Codebase maintenance** | Refactoring, dependency upgrades, security fixes |

### Feedback & Iteration

**How to iterate**:

1. Agent creates initial PR and updates description with changes
2. You comment on PR (mention `@copilot` explicitly)
3. Agent resubmits feedback to language model
4. Agent responds with updated changes

⚠️ **Your responsibility**: Review and validate responses for accuracy and appropriateness

## How the Agent Works (End-to-End)

| Stage                          | What Happens                                                                    | Details                                                                                             |
| ------------------------------ | ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **1. Prompt Processing**       | Task combined with contextual info to form prompt                               | Inputs: plain language, code snippets, or images from issue/PR comment/Copilot Chat                 |
| **2. Language Model Analysis** | LLM analyzes input to reason on task and leverage tools                         | Helps agent understand what to do and which tools to use                                            |
| **3. Response Generation**     | LLM generates response based on analysis                                        | Output: natural language suggestions and code suggestions                                           |
| **4. Output Formatting**       | Agent updates PR description with changes, includes supplemental info if needed | May note resources it couldn't access and suggest resolution steps; responds to `@copilot` mentions |

### Quality & Safety

**Intended outcome**: Most relevant solution for task resolution

**Reality check**: May not always provide the answer you're looking for

**Your role**: Responsible for reviewing and validating responses

**GitHub's role**: Red teaming (testing) to understand and improve agent safety

## Use Cases for Copilot Coding Agent

| Use Case                     | Tasks                                            |
| ---------------------------- | ------------------------------------------------ |
| **Codebase Maintenance**     | Security fixes, dependency upgrades, refactoring |
| **Documentation**            | Updating and creating new documentation          |
| **Feature Development**      | Implementing incremental feature requests        |
| **Improving Test Coverage**  | Developing additional test suites for QA         |
| **Prototyping New Projects** | Green fielding new concepts                      |

## Improving Performance for Copilot Coding Agent

### 1. Ensure Tasks Are Well-Scoped

**Provide**:

| Element                 | What to Include                   | Example                                     |
| ----------------------- | --------------------------------- | ------------------------------------------- |
| **Clear description**   | Problem to solve or work required | "Fix null pointer exception in UserService" |
| **Acceptance criteria** | What a good solution looks like   | "Should include unit tests for edge cases"  |
| **Hints/pointers**      | Files that need to be changed     | "Check `src/services/UserService.ts`"       |

### 2. Customize with Additional Context

**Add custom Copilot instructions** so agent understands:

- How to build
- How to test
- How to validate changes

**Other helpful customizations**:

- Customize development environment (`.github/workflows/copilot-setup-steps.yml`)
- Customize/disable firewall
- Extend with Model Context Protocol (MCP)

### 3. Use as a Tool, Not a Replacement

⚠️ **Always review and test** generated content to ensure:

- Meets requirements
- Free of errors
- Free of security concerns

**Before merging**: Thorough validation required

### 4. Use Secure Coding & Code Review Practices

| Practice                              | Why                                                        |
| ------------------------------------- | ---------------------------------------------------------- |
| **Avoid hard-coded secrets**          | Agent may generate syntactically correct but insecure code |
| **Prevent injection vulnerabilities** | Continue following secure coding best practices            |
| **Apply rigorous testing**            | Validate functionality and edge cases                      |
| **IP scanning**                       | Check for intellectual property issues                     |
| **Vulnerability checks**              | Security scanning before merge                             |

⚠️ **Important**: Agent can generate syntactically correct code that is NOT secure

### 5. Provide Feedback

**When you encounter issues**:

- Click thumbs-down icon below agent response
- Share feedback in community discussion forum

**Purpose**: Help improve the agent over time

### 6. Stay Up to Date

**Why**: Copilot coding agent is evolving

**Action**: Monitor new security risks and best practices as they emerge

## Security Measures for Copilot Coding Agent

### Avoiding Privilege Escalation

| Measure                        | Protection                                           |
| ------------------------------ | ---------------------------------------------------- |
| **Write access required**      | Agent only responds to users with write access       |
| **Workflow approval required** | Actions workflows need approval before running       |
| **Hidden character filtering** | Filters hidden characters to reduce prompt injection |

### Constraining Copilot's Permissions

| Constraint                   | What It Means                                              |
| ---------------------------- | ---------------------------------------------------------- |
| **Repository access**        | Only accesses repo where creating PR; cannot access others |
| **Branch restrictions**      | Pushes limited to `copilot/` branches (not default branch) |
| **Secrets/variables**        | No access to org/repo Actions secrets at runtime           |
| **Copilot environment only** | Only secrets/variables in `copilot` environment are passed |

### Preventing Data Exfiltration

**Default protection**: Firewall enabled by default

**Purpose**: Prevent accidental or malicious exfiltration of code or sensitive data

**Customization**: Can customize or disable per organizational policy

📚 **See**: [Customizing or disabling the firewall](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/4-customize-extend-validate-copilot-code-agent)

## Limitations of Copilot Coding Agent

⚠️ **Performance varies** depending on codebase and inputs

### Key Limitations

| Limitation                  | Impact                                                           | What to Do                                     |
| --------------------------- | ---------------------------------------------------------------- | ---------------------------------------------- |
| **Limited scope & quality** | LLM may not handle certain structures or obscure languages       | Quality varies by language coverage            |
| **Potential biases**        | Training data may include biases                                 | Agent may lean toward certain languages/styles |
| **Security risks**          | Generated code based on repo context could expose sensitive info | Thorough review required                       |
| **Inaccurate code**         | Code may appear correct but be semantically/syntactically wrong  | Validate fit, patterns, and style              |
| **Public code matches**     | May produce matches/near-matches even if "Block" is set          | References may not be provided                 |
| **Legal/regulatory**        | Compliance requirements vary                                     | Ensure compliance with obligations             |

### Understanding Each Limitation

**Limited Scope & Quality**:

- LLM struggles with certain code structures
- Obscure languages have lower quality output
- Performance varies by language coverage in training data

**Potential Biases**:

- Training data and retrieved context may include biases
- Agent may prefer certain languages or coding styles
- Be aware of these tendencies when reviewing

**Security Risks**:

- Generated code based on repository context
- Could expose sensitive information if not reviewed
- **Solution**: Thorough review required before merge

**Inaccurate Code**:

- May appear syntactically correct
- Could be semantically wrong or misaligned with intent
- **Solution**: Validate fit, patterns, and style manually

**Public Code Matches**:

- May produce code matching public repositories
- Happens even if "Block matching public code" is set
- References may not be provided
- **Implication**: Potential IP concerns

**Legal/Regulatory**:

- Must ensure compliance with applicable obligations
- Avoid prohibited uses under terms of service
- Follow codes of conduct

## Responsible Use Framework

### Scoping Tasks Well

✅ **Do**:

- Provide clear problem descriptions
- Include complete acceptance criteria
- Add hints about files to change
- Specify testing requirements

❌ **Don't**:

- Use vague or ambiguous descriptions
- Skip acceptance criteria
- Assume agent knows project structure
- Leave testing expectations unclear

### Securing Environments

✅ **Do**:

- Use default firewall protection
- Limit secrets to `copilot` environment only
- Leverage branch restrictions (`copilot/` branches)
- Require workflow approval before Actions run

❌ **Don't**:

- Disable firewall without organizational policy approval
- Give agent access to all secrets
- Allow pushes to default branch
- Auto-run Actions workflows

### Validating Outcomes

✅ **Do**:

- Review all generated code manually
- Run tests before merging
- Check for security vulnerabilities
- Verify fit with project patterns
- Scan for IP issues

❌ **Don't**:

- Merge without review
- Skip testing
- Ignore security scanning
- Assume code is production-ready
- Trust without verification

## Best Practices Summary

| Category            | Best Practice                                                 |
| ------------------- | ------------------------------------------------------------- |
| **Task Definition** | Clear description + acceptance criteria + file hints          |
| **Context**         | Add custom instructions via `.github/copilot-instructions.md` |
| **Tool Mindset**    | Use as assistant, not replacement                             |
| **Security**        | Follow secure coding practices, scan before merge             |
| **Review**          | Manual inspection + testing + vulnerability checks            |
| **Feedback**        | Report issues via thumbs-down or community forum              |
| **Monitoring**      | Stay updated on new risks and best practices                  |

## Security Measures Summary

| Measure Type               | Protections                                         |
| -------------------------- | --------------------------------------------------- |
| **Privilege Escalation**   | Write access required, workflow approval, filtering |
| **Permission Constraints** | Repo-scoped, branch limits, no default secrets      |
| **Data Exfiltration**      | Default firewall, customizable per policy           |

## Performance Improvement Checklist

- [ ] Provide clear, specific task descriptions
- [ ] Include complete acceptance criteria
- [ ] Add hints about files to modify
- [ ] Customize with `.github/copilot-instructions.md`
- [ ] Use MCP for extended capabilities
- [ ] Preseed environment with dependencies
- [ ] Always review and test generated code
- [ ] Apply secure coding best practices
- [ ] Run CI/CD checks before merge
- [ ] Provide feedback on issues
- [ ] Monitor evolving best practices

## Key Takeaways

✅ **Agent capabilities**: Autonomous, asynchronous, handles bug fixes, features, docs, tests, prototypes
✅ **How it works**: Prompt → LLM analysis → Response → Output formatting (iterates with `@copilot`)
✅ **Well-scoped tasks**: Clear description + acceptance criteria + file hints = better results
✅ **Custom context**: Use `.github/copilot-instructions.md` to guide agent behavior
✅ **Tool, not replacement**: Always review, test, and validate before merging
✅ **Secure practices**: Follow secure coding, scan for vulnerabilities, avoid hard-coded secrets
✅ **Security measures**: Write access gated, branch restrictions, firewall protection, no default secrets
✅ **Limitations exist**: Quality varies by language, potential biases, security risks, inaccurate code possible
✅ **Your responsibility**: Validate accuracy, security, compliance before merge
⚠️ **Legal/regulatory**: Ensure compliance with obligations and terms of service

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-code-agent/5-responsible-use-github-copilot-code-agent-github)
