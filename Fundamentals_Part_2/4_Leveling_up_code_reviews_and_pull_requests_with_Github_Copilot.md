# What GitHub Copilot adds to the review process

## Overview

Code reviews and pull request reviews are essential for quality, but can be time-consuming and uneven.

**Challenges**:

- Juggling multiple languages
- Inconsistent formatting
- Large diffs
- Providing thoughtful feedback

**Solution**: GitHub Copilot acts as collaborative reviewer and assistant

## What Copilot Does in Reviews

| Role                      | Benefit                                |
| ------------------------- | -------------------------------------- |
| **Catches common issues** | Identifies problems automatically      |
| **Drafts comments**       | Generates clear, actionable feedback   |
| **Summarizes PRs**        | Provides context for reviewers         |
| **Highlights security**   | Flags security risks proactively       |
| **Custom instructions**   | Ensures consistency across teams/repos |

**Result**: Reviewers get a clear starting point, not guesswork

## Key Features of Copilot in Code Reviews

### 5 Core Features

| Feature                       | What It Does                                                 | Benefit                                     |
| ----------------------------- | ------------------------------------------------------------ | ------------------------------------------- |
| **PR Summaries**              | Auto-drafts PR descriptions with summary + affected files    | Reviewers start with context                |
| **Security Fixes**            | Flags vulnerabilities + offers inline patches                | Aligned with repository security guidelines |
| **Line-by-Line Explanations** | Explains functionality when you highlight code               | Understand unfamiliar code quickly          |
| **Drafting Comments**         | Generates review comments based on best practices/guidelines | Clear, actionable feedback                  |
| **Reviews in Your IDE**       | Review code in IDE before opening PR                         | Catch issues early, reduce rework           |

### Security Fixes Example

**Integration**: Copilot code review + GitHub Code Scanning

**JavaScript example**:

```javascript
// ❌ Security issue detected
eval(userInput); // Unsafe!
```

**Copilot comment**:

> "eval() with user input can lead to code injection. Replace it with a safe parser like JSON.parse()."

**Then offers inline patch** aligned with your repository's security guidelines

### Reviews in Your IDE

**Where**: Inside your IDE (not just GitHub.com)

**When**: Before opening pull request

**Benefits**:

- ✅ Catch issues early
- ✅ Resolve problems before PR
- ✅ Speed up review process
- ✅ Reduce rework

## How PRUs Unlock Advanced Review Capabilities

### PRU-Powered Reviews

| Feature                    | PRU Usage                              | What You Get                                          |
| -------------------------- | -------------------------------------- | ----------------------------------------------------- |
| **Copilot as PR reviewer** | 1 PRU each time it posts comments      | Automated, intelligent feedback                       |
| **Custom instructions**    | Uses `.github/copilot-instructions.md` | Aligns with team rules (readability, security, style) |

### Example: Vague vs. Specific Feedback

**Without Copilot**:

```
❌ Reviewer comment: "Fix security issue here"
```

**With Copilot + PRUs**:

```
✅ Copilot comment: "The use of exec() introduces a code injection vulnerability.
Consider replacing it with subprocess.run() for safer command execution.
Here's a suggested patch:"

[Inline code fix provided]
```

**Difference**: Vague → Specific, actionable feedback with code examples

## Five Ways Copilot Review Helps Developers

| Method                         | How It Helps                            |
| ------------------------------ | --------------------------------------- |
| **1. Code review suggestions** | Generates concrete improvements         |
| **2. Multi-language reviews**  | Reviews code across different languages |
| **3. Formatting data**         | Cleans up tables and formatting in PRs  |
| **4. PR summaries**            | Writes effective PR descriptions        |
| **5. Explaining code**         | Helps understand unfamiliar code        |

## 1. Using Copilot Suggestions in Code Reviews

### The Problem

You spot areas for improvement but don't have time to draft perfect examples

### The Solution

**In "Files changed" view**:

1. Highlight line or block of code
2. Ask Copilot to suggest improvements or flag issues
3. Copilot generates context-aware suggestion
4. Copy into review comment

### Example: Ruby Refactoring

**Scenario**: Reviewing Ruby file with repeated logic

**You ask**:

```
"Suggest a cleaner Ruby refactor for this repeated code."
```

**Copilot provides**:

- Updated version following Ruby best practices
- Concrete, actionable suggestion
- You paste into review with your explanation

### Key Benefit

✅ **You stay focused on**: Overall quality and design
✅ **Copilot handles**: Actionable, high-value feedback
❌ **Doesn't blur line**: Reviewing vs coding on author's behalf

## 2. Reviewing Across Multiple Languages

### The Challenge

Reviewing code outside your primary area of expertise

### How Copilot Helps

| Feature                           | Benefit                                          |
| --------------------------------- | ------------------------------------------------ |
| **Highlights non-best practices** | Flags code not following language conventions    |
| **Generates improvements**        | Proposes fixes aligned with language conventions |
| **Enables broader reviews**       | Give stronger feedback outside expertise area    |

### Example: Go Code Review

**Scenario**: Reviewing Go code when Go isn't your primary language

**Copilot spots**: Variable declaration that doesn't follow Go best practices

**Suggests**: Replace with short variable declaration (idiomatic Go)

**Result**: Accurate review feedback even outside your expertise

## 3. Formatting Data for Pull Requests

### The Problem

PRs with poorly formatted context (metrics, screenshots, test results)

### How Copilot Helps as "Second Set of Eyes"

| Action                   | What Copilot Does                                    |
| ------------------------ | ---------------------------------------------------- |
| **Flags bad formatting** | Identifies poorly formatted tables in PR description |
| **Proposes fix**         | Provides cleaner version aligned with style guide    |
| **Applies guidelines**   | Uses `.github/copilot-instructions.md`               |

### Example: Table Formatting

**Before (hard to read)**:

| Test Run | LoadTimeBefore | LoadTimeAfter |
| -------- | -------------- | ------------- |
| 1.3      | 1.2            |               |
| 1.2      | 1.1            |               |
| 1.1      | 0.885          |               |
| 1.3      | 1.3            |               |
| 1.2      | 0.918          |               |
| Average  | 1.22           | 1.0806        |

**Copilot comment**:

> "This table doesn't follow your repository's Markdown guidelines. Here's a cleaned-up version based on your company's style guide."

**After (clean, readable)**:

| Test Run    | Load Time Before (seconds) | Load Time After Updates (seconds) |
| ----------- | -------------------------- | --------------------------------- |
| 1           | 1.3                        | 1.2                               |
| 2           | 1.2                        | 1.1                               |
| 3           | 1.1                        | 0.885                             |
| 4           | 1.3                        | 1.3                               |
| 5           | 1.2                        | 0.918                             |
| **Average** | **1.22**                   | **1.0806**                        |

**Reviewer action**: Accept suggestion with one click

**Result**: PR follows company style without manual reformatting

### Role Clarification

⚠️ **Copilot acts as automatic reviewer** (not coding agent):

- Sees unformatted content
- Applies company guidelines from `.github/copilot-instructions.md`
- Supplies corrected version inline

## 4. Writing Effective Pull Request Summaries

### The Challenge

Writing PR descriptions feels like a hurdle (often last step in process)

### How Copilot Helps

**From PR description editor**:

1. Click Copilot icon
2. Choose:
   - **Generate summary** - Full PR description
   - **Generate outline** - Structured framework

**Result**: Well-structured starting point

### Benefits

| Benefit                  | Impact                               |
| ------------------------ | ------------------------------------ |
| **Saves time**           | Don't start from blank page          |
| **Ensures completeness** | Reviewers have information they need |
| **Allows customization** | Edit generated content as needed     |
| **Consistent structure** | All PRs follow similar format        |

## 5. Explaining and Reviewing Code

### Two Use Cases

**Use Case 1: Understanding unfamiliar code in PR**

**Problem**: Reviewing code you don't fully understand

**Solution**: Ask Copilot to explain the changes

**Benefit**: No more struggling through unfamiliar code

**Use Case 2: Self-review before requesting feedback**

**Problem**: Want to catch issues before teammates review

**Solution**: Copilot runs initial review of your own PRs

**Benefits**:

- ✅ Catches smaller issues
- ✅ Validates best practices
- ✅ Increases confidence in submission quality
- ✅ Reduces back-and-forth with reviewers

## Copilot Review Workflow

### Traditional Review Workflow

```
1. Developer opens PR
2. Reviewer reads through all code
3. Reviewer writes comments manually
4. Vague feedback ("fix this")
5. Developer asks for clarification
6. Multiple review rounds
```

### Enhanced Workflow with Copilot

```
1. Developer self-reviews with Copilot in IDE
2. Copilot catches issues early
3. Developer fixes before opening PR
4. PR opened with Copilot-generated summary
5. Copilot assigned as reviewer
6. Copilot posts specific, actionable comments
7. Human reviewer focuses on high-level design
8. Faster approval with fewer rounds
```

## Custom Review Instructions

### Using `.github/copilot-instructions.md`

**Purpose**: Guide Copilot to watch for same patterns you do

**Benefits**:

| Benefit                 | Impact                                 |
| ----------------------- | -------------------------------------- |
| **Consistency**         | Across teams and repositories          |
| **Team alignment**      | Reviews follow team rules              |
| **Focus areas**         | Readability, security, style, etc.     |
| **Automated standards** | No manual checking of style guidelines |

**Example instructions**:

```markdown
# Code Review Guidelines

## Security

- Flag any use of eval(), exec(), or subprocess without sanitization
- Require input validation for all user-provided data

## Style

- Enforce 80-character line length
- Require descriptive variable names (no single letters except loops)

## Performance

- Highlight N+1 query patterns
- Flag synchronous operations that could be async
```

## Where Copilot Reviews Work

| Location       | When to Use                | Benefit                   |
| -------------- | -------------------------- | ------------------------- |
| **GitHub.com** | During PR review process   | Full team visibility      |
| **Your IDE**   | Before opening PR          | Catch issues early        |
| **Both**       | Complete workflow coverage | Maximum quality assurance |

## PRU Consumption Summary

| Activity                  | PRU Cost | When It Applies                  |
| ------------------------- | -------- | -------------------------------- |
| **PR summary generation** | 1-2 PRUs | When generating PR description   |
| **Copilot as reviewer**   | 1 PRU    | Each time it posts comments      |
| **Security scanning**     | 1-3 PRUs | Comprehensive vulnerability scan |
| **Code explanations**     | 1 PRU    | Per explanation request          |

## Key Advantages

| Advantage                  | Impact                                      |
| -------------------------- | ------------------------------------------- |
| **Time savings**           | Less time writing comments manually         |
| **Consistency**            | Same standards across all reviews           |
| **Security focus**         | Automatically flags vulnerabilities         |
| **Multi-language support** | Review code outside your expertise          |
| **Early detection**        | Catch issues in IDE before PR               |
| **Better feedback**        | Specific, actionable comments with examples |

## Review Quality Comparison

### Without Copilot

- ❌ Vague comments
- ❌ Inconsistent feedback across reviewers
- ❌ Security issues might be missed
- ❌ Time-consuming to write detailed feedback
- ❌ Difficult to review unfamiliar languages

### With Copilot

- ✅ Specific, actionable comments
- ✅ Consistent standards via custom instructions
- ✅ Security issues automatically flagged
- ✅ Generated feedback with code examples
- ✅ Multi-language support

## Best Practices

| Practice                       | Why It Matters                                |
| ------------------------------ | --------------------------------------------- |
| **Use custom instructions**    | Ensures Copilot follows your team's standards |
| **Self-review with Copilot**   | Catch issues before teammates review          |
| **Review in IDE first**        | Earlier detection = less rework               |
| **Generate PR summaries**      | Saves time, ensures completeness              |
| **Let Copilot draft comments** | More specific feedback faster                 |
| **Use for multi-language PRs** | Get accurate feedback outside expertise       |

## Key Takeaways

✅ **5 core features**: PR summaries, security fixes, explanations, comment drafting, IDE reviews
✅ **PRU-powered**: Advanced capabilities with specific, actionable feedback
✅ **5 ways to help**: Suggestions, multi-language, formatting, summaries, explanations
✅ **Custom instructions**: Guide Copilot to follow team patterns (`.github/copilot-instructions.md`)
✅ **Security integration**: Integrated with GitHub Code Scanning for vulnerability detection
✅ **Multi-language support**: Review code outside your primary expertise
✅ **Early detection**: Catch issues in IDE before opening PR
✅ **Time savings**: Auto-generate summaries, format data, draft comments
✅ **Consistency**: Same standards across all reviews and reviewers
✅ **Actionable feedback**: Specific comments with inline patches, not vague "fix this"

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/code-reviews-pull-requests-github-copilot/2-github-copilot-review-process)

# Using Copilot as a reviewer in GitHub.com

## Overview

Requesting a Copilot review on GitHub.com is simple - add it from the Reviewers menu like any teammate.

**Key characteristics**:

- ⚡ Completes in seconds (typically <30s)
- 💬 Generates comment reviews (not approvals/rejections)
- 🚫 Never blocks merges
- 🎯 Adds valuable context for human reviewers

## How Copilot Reviews Work

| Aspect                 | Details                                                 |
| ---------------------- | ------------------------------------------------------- |
| **Type of review**     | Comment review only (not approval or rejection)         |
| **Merge blocking**     | Never blocks merges                                     |
| **Required approvals** | Comments don't count toward required approvals          |
| **Customization**      | Use `copilot-instructions.md` for team guidelines       |
| **Comment behavior**   | Behave like teammate comments (react, resolve, comment) |

## What Copilot Might Flag

| Issue Type             | Example                                      |
| ---------------------- | -------------------------------------------- |
| **Missing type hints** | Function parameters without type annotations |
| **Formatting issues**  | Inconsistent indentation or style            |
| **Potential bugs**     | Logic errors or edge cases                   |
| **Security risks**     | Unsafe function usage (eval, exec)           |
| **Best practices**     | Non-idiomatic code patterns                  |

## How to Request a Code Review on GitHub.com (6 Steps)

### Step-by-Step Process

| Step | Action                      | Details                                   | Time        |
| ---- | --------------------------- | ----------------------------------------- | ----------- |
| 1    | **Open/create PR**          | Create new PR or navigate to existing one | Immediate   |
| 2    | **Add Copilot as reviewer** | Reviewers menu → Select **Copilot**       | Immediate   |
| 3    | **Wait for review**         | Copilot analyzes PR automatically         | <30 seconds |
| 4    | **Review comments**         | Scroll through to read Copilot's feedback | As needed   |
| 5    | **Apply suggested changes** | Commit fixes directly from PR interface   | As needed   |
| 6    | **Understand limits**       | Remember Copilot's advisory role          | N/A         |

### Step 1: Open or Create a Pull Request

**What to do**:

- Create new pull request, OR
- Navigate to existing PR in your repository

**When**: Start of review process

### Step 2: Add Copilot as Reviewer

**How**: In the **Reviewers** menu → Select **Copilot**

**Like**: Assigning a human teammate

**Visual**: Reviewers panel shows Copilot suggested as "AI pair programmer reviewer"

### Step 3: Wait for Review to Complete

**Timeline**: Typically completes in **less than 30 seconds**

**What happens**: Copilot begins analyzing your PR right away

**Benefit**: Get results quickly without interrupting workflow

### Step 4: Review Copilot's Comments

**How to access**: Scroll through the pull request

**What you'll see**: Suggestions left as comments on relevant lines of code

**Example**: Screenshot shows Copilot suggesting correction:

- From: `random_greetin` (misspelled)
- To: `random_greeting` (corrected)
- Language: Ruby file

### Step 5: Apply Copilot's Suggested Changes

**Two methods**:

| Method                 | When to Use                        | How                            |
| ---------------------- | ---------------------------------- | ------------------------------ |
| **Direct commit**      | Copilot flags issues directly      | Commit fixes from PR interface |
| **Generate solutions** | Responding to peer review comments | Ask Copilot to suggest fix     |

#### Example: Using Copilot to Generate Solutions

**Scenario**: Peer reviewer comments: "Replace `exec()` with a safer function"

**Your prompt**:

```
"Suggest a fix for this review comment: Replace exec() with a safer function."
```

**Copilot proposes**: Patch using `subprocess.run()`

**Your workflow**:

1. Test locally
2. Commit the fix
3. Ensure tests pass

**PRU benefit**: Analyzes review comments + code context → High-quality solutions

### Step 6: Understanding the Limits

**Copilot's role**: Advisory only

| What Copilot Does                   | What Copilot Doesn't Do            |
| ----------------------------------- | ---------------------------------- |
| ✅ Catches issues early             | ❌ Approve or reject pull requests |
| ✅ Generates actionable suggestions | ❌ Count toward required approvals |
| ✅ Speeds up routine checks         | ❌ Make architectural decisions    |
| ✅ Provides context                 | ❌ Handle nuanced trade-offs       |
| ✅ Flags common problems            | ❌ Give final sign-off             |

**Human reviewers needed for**:

- Architectural decisions
- Nuanced trade-offs
- Final sign-off
- Business logic validation
- Strategic direction

## Comment Interaction

### How Review Comments Behave

**Like teammate comments** - You can:

| Action      | How It Works                           |
| ----------- | -------------------------------------- |
| **React**   | Add emoji reactions (👍, 👎, 🎉, etc.) |
| **Resolve** | Mark comments as resolved              |
| **Reply**   | Comment on Copilot's feedback          |
| **Discuss** | Have threaded conversations            |

### Comment Types Examples

**Type hints example**:

```python
# Copilot flags missing type hints
def calculate_total(items):  # ❌ No type hints
    return sum(items)

# Copilot suggests:
def calculate_total(items: list[float]) -> float:  # ✅ With type hints
    return sum(items)
```

**Formatting example**:

```ruby
# Copilot flags misspelled variable
random_greetin = "Hello"  # ❌ Typo

# Copilot suggests:
random_greeting = "Hello"  # ✅ Corrected
```

## Customizing Copilot's Behavior

### Using `copilot-instructions.md`

**Location**: `.github/copilot-instructions.md` in your repository

**Purpose**: Guide Copilot to follow your team's specific review guidelines

**Benefits**:

| Benefit            | Impact                               |
| ------------------ | ------------------------------------ |
| **Team alignment** | Copilot looks for same things you do |
| **Consistency**    | Standards applied across all reviews |
| **Customization**  | Tailored to your team's needs        |

**Example instructions**:

```markdown
# Our Team's Review Guidelines

## Required Checks

- All functions must have type hints
- Variable names must be descriptive (no single letters)
- Security: Flag any use of eval() or exec()

## Style Guidelines

- 80-character line limit
- Use descriptive variable names
- Follow PEP 8 (Python) or team style guide

## Performance

- Flag N+1 query patterns
- Highlight synchronous operations that could be async
```

## PRU-Powered Fixes

### How PRUs Enhance Reviews

**Without PRUs**:

- Basic pattern matching
- Limited context understanding

**With PRUs**:

- Analyzes review comments alongside code context
- Proposes high-quality, contextual solutions
- Faster, smarter fixes

### Example: PRU-Powered Security Fix

**Review comment**: "Replace `exec()` with safer function"

**Without PRUs**: Generic suggestion

**With PRUs**:

```python
# Copilot analyzes context and proposes:
# Before (unsafe):
exec(user_command)

# After (safe):
import subprocess
result = subprocess.run(user_command, shell=False, capture_output=True, text=True)
```

**Includes**:

- Specific function (`subprocess.run`)
- Security best practices (`shell=False`)
- Context-appropriate parameters

## Review Speed Comparison

| Review Type               | Time Required  | Context                |
| ------------------------- | -------------- | ---------------------- |
| **Copilot review**        | <30 seconds    | Automated, consistent  |
| **Quick human review**    | 5-15 minutes   | Basic checks only      |
| **Thorough human review** | 30-60+ minutes | Comprehensive analysis |

**Optimal approach**: Copilot (quick checks) + Human (strategic review) = Best results

## When to Use Copilot Reviews

### ✅ Good Use Cases

| Use Case               | Why It Works                        |
| ---------------------- | ----------------------------------- |
| **Routine checks**     | Catches common issues automatically |
| **Style consistency**  | Enforces standards                  |
| **Security basics**    | Flags obvious vulnerabilities       |
| **Quick feedback**     | Fast turnaround before human review |
| **Multi-language PRs** | Consistent checks across languages  |

### ⚠️ Limitations (Rely on Humans)

| Limitation                  | Why Human Review Needed                  |
| --------------------------- | ---------------------------------------- |
| **Architectural decisions** | Requires strategic thinking              |
| **Business logic**          | Needs domain knowledge                   |
| **Nuanced trade-offs**      | Requires experience and judgment         |
| **Final approval**          | Comments don't count toward requirements |
| **Complex refactoring**     | Needs understanding of system design     |

## Workflow Integration

### Typical Review Flow

```
1. Developer opens PR
2. Add Copilot as reviewer (Reviewers menu)
3. Copilot reviews in <30 seconds
4. Developer reads Copilot's comments
5. Developer applies suggested fixes
6. Human reviewers focus on high-level concerns
7. Faster approval process
```

### Before and After

**Traditional workflow**:

```
PR opened → Wait for human reviewer →
Review comments (vague) → Clarification needed →
Back-and-forth → Finally approved
Time: Hours to days
```

**With Copilot workflow**:

```
PR opened → Copilot reviews immediately (<30s) →
Specific, actionable comments → Developer fixes →
Human reviewer focuses on architecture →
Faster approval
Time: Minutes to hours
```

## Review Comment Examples

### Example 1: Security Issue

**Copilot comment**:

> "⚠️ Security: `eval()` with user input can lead to code injection. Replace with `JSON.parse()` for safe parsing."

**Suggested fix**:

```javascript
// Before:
const data = eval(userInput);

// After:
const data = JSON.parse(userInput);
```

### Example 2: Type Hints

**Copilot comment**:

> "💡 Add type hints to improve code clarity and catch type errors early."

**Suggested fix**:

```python
# Before:
def calculate_tax(amount, rate):
    return amount * rate

# After:
def calculate_tax(amount: float, rate: float) -> float:
    return amount * rate
```

### Example 3: Formatting

**Copilot comment**:

> "✨ Variable name typo: `random_greetin` should be `random_greeting`"

**Suggested fix**: Correct spelling

## Where to Go Next

**Catch even more issues before code reaches GitHub**: Use Copilot in your IDE

| Location       | When              | Benefit                      |
| -------------- | ----------------- | ---------------------------- |
| **IDE**        | Before opening PR | Catch issues earliest        |
| **GitHub.com** | During PR review  | Team visibility + automation |

## Quick Reference: Using Copilot on GitHub.com

**Add as reviewer**:

```
Reviewers menu → Select "Copilot"
```

**Review completes**: <30 seconds

**Comment types**:

- Type hints
- Formatting
- Security
- Best practices
- Bugs

**Apply fixes**: Direct commit or ask Copilot to generate solution

**Remember**: Advisory only (doesn't approve/reject PRs)

## Key Takeaways

✅ **Simple to request**: Add from Reviewers menu like any teammate
✅ **Fast reviews**: Completes in <30 seconds typically
✅ **Comment reviews only**: Never approves/rejects or blocks merges
✅ **Customizable**: Use `copilot-instructions.md` for team guidelines
✅ **Interactive comments**: React, resolve, reply like teammate comments
✅ **Common flags**: Type hints, formatting, bugs, security issues
✅ **PRU-powered**: Analyzes context for high-quality suggestions
✅ **Advisory role**: Doesn't count toward required approvals
✅ **Human review still needed**: For architecture, trade-offs, final sign-off
⚠️ **Limitations understood**: Use for routine checks, not strategic decisions

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/code-reviews-pull-requests-github-copilot/3-copilot-reviewer-github)

# Catching issues early and automating reviews with Copilot

## Overview

GitHub Copilot reviews don't have to wait until you open a pull request.

**Key capabilities**:

- Review changes locally in VS Code or JetBrains IDEs before committing
- Address style violations, security gaps, best practices earlier
- Configure automatic reviews for all pull requests
- Scale across repositories and teams

**Result**: Save cycles in the review process

## What You'll Learn

| Capability                     | Benefit                               |
| ------------------------------ | ------------------------------------- |
| **Local IDE reviews**          | Catch issues before pushing code      |
| **Path-specific instructions** | Customize behavior for specific files |
| **PRU-powered analysis**       | Deeper insights with advanced models  |
| **Automatic PR reviews**       | Scale reviews across teams            |
| **Rulesets + status checks**   | Create comprehensive review pipelines |
| **Automation at scale**        | Consistent reviews for all changes    |

## Running Copilot Reviews Locally in Your IDE

### Where It Works

| IDE           | Support | When to Use            |
| ------------- | ------- | ---------------------- |
| **VS Code**   | ✅ Full | Before committing code |
| **JetBrains** | ✅ Full | During development     |

### Setting Up Local Reviews

**Create**: `.github/copilot-instructions.md`

**Example rules**:

```markdown
# Code Review Guidelines

- Focus on security and avoid unsafe string interpolation
- Ensure functions have docstrings explaining parameters and return types
- Flag repetitive code patterns
- Enforce 80-character line limit
```

**How it works**: Copilot applies these rules automatically to analyze larger diffs and provide context-rich insights aligned with your repo's style

### Use Case Example: TypeScript Service

**Scenario**: Developer adds repetitive code in TypeScript service

**Without local review**:

```
Developer writes code → Pushes → Opens PR →
Peer reviewer spots repetition → Requests changes →
Developer fixes → Pushes again
Time: Hours to days
```

**With local Copilot review**:

```
Developer writes code → Copilot flags repetition →
Suggests extracting helper function → Developer fixes immediately →
Pushes clean code
Time: Minutes
```

**Benefit**: Reduces review noise, catches issues earlier

## Creating Path-Specific Custom Instructions

### What Are Path-Specific Instructions?

**Purpose**: Guide Copilot code review or coding agent for specific files or folders

**Location**: `.github/instructions/`

### Setup Process (4 Steps)

| Step | Action                        | Details                                           |
| ---- | ----------------------------- | ------------------------------------------------- |
| 1    | Create instructions directory | Add `.github/instructions` folder in repo root    |
| 2    | Add instruction files         | Create files ending in `.instructions.md`         |
| 3    | Define paths                  | Add frontmatter with `applyTo` keyword            |
| 4    | Write custom guidance         | Add review guidance in Markdown below frontmatter |

### Step 1: Create Instructions Directory

**Location**: Root of your repository

**Folder name**: `.github/instructions`

**If exists**: Skip to step 2

### Step 2: Add Instruction Files

**Naming convention**: `[purpose].instructions.md`

**Examples**:

- `security.instructions.md`
- `performance.instructions.md`
- `ruby-models.instructions.md`

**Purpose**: File name describes the purpose of instructions

### Step 3: Define Paths to Apply To

**Method**: Add frontmatter block with `applyTo` keyword

**Syntax**: Use glob patterns to target files/directories

#### Examples

**Apply to Ruby models**:

```markdown
---
applyTo: "app/models/**/*.rb"
---
```

**Apply to TypeScript files**:

```markdown
---
applyTo: "**/*.ts,**/*.tsx"
---
```

**Apply to all files**:

```markdown
---
applyTo: "**"
---
```

### Step 4: Write Custom Guidance

**Format**: Plain language using Markdown below frontmatter

**Flexibility**: Write as paragraph, separate lines, or with blank lines for readability

**Behavior**: Copilot follows these instructions when reviewing or generating code for matching paths

### Complete Example: Security Instructions for Ruby Models

```markdown
---
applyTo: "app/models/**/*.rb"
---

# Security Guidelines for Ruby Models

## Required Checks

- Always use parameterized queries (no string interpolation in SQL)
- Validate all user input before database operations
- Use strong_parameters for mass assignment protection

## Best Practices

- Include has_secure_password for authentication models
- Use scope validations to prevent unauthorized access
- Sanitize all output displayed in views
```

## Path-Specific Instructions: Glob Pattern Reference

| Pattern              | Matches                         | Use Case                |
| -------------------- | ------------------------------- | ----------------------- |
| `**/*.py`            | All Python files                | Python-specific rules   |
| `src/**/*.ts`        | TypeScript files in src/        | Frontend-specific rules |
| `app/models/**/*.rb` | Ruby models                     | Model-specific security |
| `**/*.test.js`       | All test files                  | Testing standards       |
| `**/security/**/*`   | Files in any security directory | Security-critical code  |
| `**`                 | All files in repository         | Global rules            |

## Leverage PRUs for Deeper Analysis in Your IDE

### Lightweight vs PRU-Powered Reviews

**Lightweight checks (GitHub.com)**:

- Basic pattern matching
- Surface-level analysis
- Fast but limited

**PRU-powered reviews (IDE)**:

- Advanced model analysis
- Larger diff handling
- Custom instruction application
- Higher-quality suggestions

### PRU-Powered Benefits

| Benefit                    | Impact                               |
| -------------------------- | ------------------------------------ |
| **Advanced models**        | Tap into more sophisticated analysis |
| **Larger diffs**           | Analyze comprehensive code changes   |
| **Custom instructions**    | Apply repository-specific guidelines |
| **Earlier detection**      | Spot issues before PR                |
| **Context-rich analysis**  | Deeper understanding of code intent  |
| **Reduced back-and-forth** | Fewer review cycles with teammates   |

### What PRUs Enable in IDE

**Style violations**: Catch formatting issues before push

**Security gaps**: Identify vulnerabilities locally

**Best-practice issues**: Flag non-idiomatic code early

**Development cycle advantage**: Spot problems where you write and test code

**Human review preserved**: Final judgment and sign-off still with humans

### PRU Usage in IDE Reviews

**When PRU consumed**: Each local Copilot review in IDE

**Analysis depth**: More comprehensive than GitHub.com lightweight checks

**Budget consideration**: Organizations should track PRU consumption for local reviews

## Automating Reviews and Scaling with Rulesets

### The Scalability Problem

**Challenge**: Manual reviews don't scale well in fast-moving teams

**Solution**: Configure rulesets so Copilot is automatically assigned to all PRs targeting protected branches

**Benefit**: Every change gets reviewed, even if human reviewers are delayed

### Review Pipeline with Rulesets + Status Checks

**Create a comprehensive pipeline**:

| Component           | What It Checks        | Benefit              |
| ------------------- | --------------------- | -------------------- |
| **Copilot reviews** | Style and readability | Consistent standards |
| **Code scanning**   | Vulnerabilities       | Security assurance   |
| **Tests**           | Functionality         | Feature validation   |

**Pipeline flow**:

```
PR opened → Copilot reviews (style/readability) →
Code scanning (security) → Tests (functionality) →
Human review (architecture) → Merge
```

### PRU Budget Management

**Consideration**: Each Copilot review uses PRUs

**Organization strategy**:

| Action                     | Purpose                              |
| -------------------------- | ------------------------------------ |
| **Budget PRU consumption** | Match review volume                  |
| **Timing optimization**    | Perform reviews at appropriate times |
| **Usage tracking**         | Balance cost and coverage            |

### Automation Benefits

**Even small changes reviewed**:

- Small fixes
- Dependency updates
- Configuration changes

**Result**: Reduces risk of unnoticed regressions

## Three Levels of Automatic Reviews

| Level            | Scope          | Who Can Configure    | Plan Required |
| ---------------- | -------------- | -------------------- | ------------- |
| **Your account** | All your PRs   | Individual developer | Pro or Pro+   |
| **Repository**   | Single repo    | Repository admin     | Any plan      |
| **Organization** | Multiple repos | Organization owner   | Any plan      |

## Automatic Reviews for Your Account

### Availability

⚠️ **Plan required**: Copilot Pro or Copilot Pro+

**Who**: Individual developers

**Scope**: Every PR you open across all repositories

### Benefits

| Benefit                   | Impact                             |
| ------------------------- | ---------------------------------- |
| **Catch issues early**    | Across all your work automatically |
| **Consistent reviews**    | Same standards everywhere          |
| **Personal quality gate** | Your own automated reviewer        |

### Setup Steps

| Step | Action                               | Details                               |
| ---- | ------------------------------------ | ------------------------------------- |
| 1    | Click profile picture                | Upper-right corner of any GitHub page |
| 2    | Select "Your Copilot"                | Opens Copilot settings                |
| 3    | Find "Automatic Copilot code review" | In settings panel                     |
| 4    | Select "Enabled" from dropdown       | Activates automatic reviews           |

**Result**: Copilot automatically added to all your future pull requests

## Automatic Reviews for a Repository

### When to Use

**Scenario**: Only want automatic reviews in certain repositories

**Example**: Production services requiring stricter quality control

**Who configures**: Repository admins

**Method**: Create a branch ruleset

### Setup Steps (7 Steps)

| Step | Action                   | Navigation/Details                                    |
| ---- | ------------------------ | ----------------------------------------------------- |
| 1    | Open repository Settings | Click Settings in repository                          |
| 2    | Navigate to Rulesets     | Left sidebar → Code and automation → Rules → Rulesets |
| 3    | Create new ruleset       | Click "New ruleset" → "New branch ruleset"            |
| 4    | Configure basic settings | Name, set to "Active", select target branches         |
| 5    | Enable PR requirement    | Check "Require a pull request before merging"         |
| 6    | Enable Copilot review    | Select "Request pull request review from Copilot"     |
| 7    | Save                     | Click "Create" at bottom                              |

### Detailed Steps

**Step 1: Open Settings**

- Navigate to repository
- Click "Settings" tab

**Step 2: Navigate to Rulesets**

- Left sidebar: expand "Code and automation"
- Select "Rules" → "Rulesets"

**Step 3: Create New Ruleset**

- Click "New ruleset"
- Choose "New branch ruleset"

**Step 4: Configure Basic Settings**

- **Ruleset name**: Descriptive name (e.g., "Require Copilot Review")
- **Enforcement status**: Set to "Active"
- **Target branches**: Select branches (e.g., "default branch")

**Step 5: Enable PR Requirement**

- Under "Branch rules"
- Check "Require a pull request before merging"

**Step 6: Enable Copilot Review**

- In expanded options
- Select "Request pull request review from Copilot"

**Step 7: Save**

- Click "Create" at bottom of page

### Optional Enhancement

**Feature**: "Require conversation resolution before merging"

**Purpose**: Encourages developers to read Copilot's feedback

**How to enable**: Check this option in branch rules

### Result

**Automatic behavior**: Every PR targeting chosen branches automatically includes Copilot's review

## Automatic Reviews Across an Organization

### When to Use

**Scenario**: Larger teams needing consistent reviews across multiple repositories

**Who configures**: Organization owners

**Benefit**: Scale review standards organization-wide

### Setup Process (10 Steps)

| Step | Action                     | Details                                          |
| ---- | -------------------------- | ------------------------------------------------ |
| 1    | Access organizations       | Profile picture → "Your organizations"           |
| 2    | Select organization        | Choose the organization                          |
| 3    | Open Settings              | Go to Settings                                   |
| 4    | Navigate to Rulesets       | Sidebar → Repository → Rulesets                  |
| 5    | Create new branch ruleset  | Click "New ruleset" → "New branch ruleset"       |
| 6    | Name and activate          | Provide name, set to "Active"                    |
| 7    | Add target repositories    | Specify inclusion/exclusion patterns             |
| 8    | Define target branches     | Select which branches to protect                 |
| 9    | Enable PR + Copilot review | Require PR before merge + Copilot review request |
| 10   | Save                       | Click "Create"                                   |

### Repository Targeting with Patterns

**Method**: Use inclusion or exclusion patterns

**Examples**:

| Pattern      | Matches                             | Use Case                   |
| ------------ | ----------------------------------- | -------------------------- |
| `*service`   | All repos ending in "service"       | All service repositories   |
| `frontend-*` | All repos starting with "frontend-" | All frontend repos         |
| `prod-*`     | All repos starting with "prod-"     | Production repositories    |
| `*`          | All repositories                    | Organization-wide standard |

### Detailed Configuration

**Step 7: Add Target Repositories**

**Inclusion patterns**: Repos that match will have ruleset applied

**Exclusion patterns**: Repos that match will be excluded

**Example configuration**:

- Include: `*service`, `*api`
- Exclude: `test-*`, `demo-*`

**Result**: All service and API repos get automatic reviews, except test/demo repos

### Organization-Wide Benefits

| Benefit                    | Impact                                  |
| -------------------------- | --------------------------------------- |
| **Consistent standards**   | Same review quality across all repos    |
| **Reduced review times**   | Automated checks speed up process       |
| **Comprehensive coverage** | No repos slip through without review    |
| **Scalable enforcement**   | Easy to add new repos matching patterns |

## Automation Levels Comparison

| Level            | Setup Complexity | Coverage       | Best For                    |
| ---------------- | ---------------- | -------------- | --------------------------- |
| **Account**      | ⚡ Easy          | Your PRs only  | Individual developers       |
| **Repository**   | ⚡⚡ Moderate    | Single repo    | Specific critical repos     |
| **Organization** | ⚡⚡⚡ Advanced  | Multiple repos | Organization-wide standards |

## Review Automation Pipeline

### Complete Automated Review Flow

```
Code pushed → Copilot review (automatic) →
Status checks (tests, scanning) →
Human review (architecture, business logic) →
Merge
```

### Pipeline Components

| Component          | Automated | Purpose                    | Tool                 |
| ------------------ | --------- | -------------------------- | -------------------- |
| **Copilot review** | ✅ Yes    | Style, readability, basics | GitHub Copilot       |
| **Tests**          | ✅ Yes    | Functionality validation   | CI/CD                |
| **Code scanning**  | ✅ Yes    | Security vulnerabilities   | GitHub Code Scanning |
| **Human review**   | ❌ No     | Architecture, trade-offs   | Team members         |

## PRU Consumption Tracking

### Why Track PRU Usage

**Reason**: Each Copilot review uses PRUs

**Goal**: Balance cost and coverage

**Strategy**: Budget PRU consumption to match review volume

### Tracking Considerations

| Metric                     | Why It Matters                  |
| -------------------------- | ------------------------------- |
| **Reviews per day**        | Understand volume               |
| **Average PRU per review** | Calculate daily/monthly costs   |
| **Peak usage times**       | Optimize review timing          |
| **Repository breakdown**   | Identify high-consumption repos |

## Best Practices for Automated Reviews

| Practice                           | Why It Matters                                |
| ---------------------------------- | --------------------------------------------- |
| **Start with critical repos**      | Prove value before scaling                    |
| **Use path-specific instructions** | Tailor reviews to code type                   |
| **Enable conversation resolution** | Ensure developers read feedback               |
| **Pair with status checks**        | Create comprehensive review pipeline          |
| **Track PRU usage**                | Manage costs effectively                      |
| **Combine with human review**      | Use Copilot for routine, humans for strategic |

## Quick Reference: Setup Summary

**Local reviews (IDE)**:

```
1. Create .github/copilot-instructions.md
2. Add review guidelines
3. Copilot applies automatically
```

**Path-specific instructions**:

```
1. Create .github/instructions/
2. Add [name].instructions.md files
3. Add frontmatter with applyTo glob pattern
4. Write guidance below frontmatter
```

**Automatic account reviews (Pro/Pro+)**:

```
Profile → Your Copilot → Automatic review → Enabled
```

**Automatic repo reviews**:

```
Repo Settings → Rulesets → New branch ruleset →
Enable PR requirement + Copilot review
```

**Automatic org reviews**:

```
Org Settings → Rulesets → New branch ruleset →
Target repos with patterns → Enable Copilot review
```

## Key Takeaways

✅ **Review before PR**: Use Copilot locally in VS Code or JetBrains IDEs
✅ **Path-specific instructions**: Customize behavior for specific files/folders (.github/instructions/)
✅ **PRU-powered depth**: Advanced models analyze larger diffs with custom instructions in IDE
✅ **Automatic reviews**: Configure at account, repository, or organization level
✅ **Rulesets for scale**: Automatically assign Copilot to all PRs targeting protected branches
✅ **Comprehensive pipelines**: Combine Copilot + code scanning + tests for complete coverage
✅ **PRU budget management**: Track usage to balance cost and coverage
✅ **Consistent standards**: Even small fixes and dependency updates get reviewed
✅ **Three automation levels**: Account (Pro/Pro+), Repository (any plan), Organization (any plan)
⚠️ **Human review essential**: Copilot handles routine, humans handle architecture and final approval

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/code-reviews-pull-requests-github-copilot/4-issues-early-automated-reviews-copilot)

# Measuring impact and optimizing premium request units (PRUs)

## Overview

**PRUs = The fuel behind Copilot's most powerful review features**

**When PRUs are used**:

- Assigning Copilot to review large pull requests
- Applying repository's custom instructions to entire codebase
- Running deep analysis of changes in your IDE

**What PRUs provide**: Additional processing power and context depth for richer reasoning, more reliable outputs, and suggestions aligned with team standards

## Learning Objectives

| Objective          | What You'll Learn                            |
| ------------------ | -------------------------------------------- |
| **Define PRUs**    | How they enable advanced review capabilities |
| **Measure impact** | Track PRU-powered review effectiveness       |
| **Optimize usage** | Budget and maximize PRU value                |

## Understanding PRUs

### What Are PRUs?

**Analogy**: Think of PRUs as tokens that unlock Copilot's "extra gear"

**Task types**:

| Task Type         | PRU Usage | Example                                  |
| ----------------- | --------- | ---------------------------------------- |
| **Lightweight**   | ❌ None   | Suggesting small refactor to single line |
| **Premium-level** | ✅ Yes    | Reviewing 1,500-line change across files |

### Premium-Level Task Requirements

**What triggers PRU usage**:

- Review large multi-file changes
- Apply `.github/copilot-instructions.md` file
- Check for security and style issues
- Scan entire diffs
- Interpret custom review guidelines
- Return actionable fixes

### Lightweight vs. PRU-Powered Analysis

| Feature                 | Without PRUs (Lightweight) | With PRUs (Premium)                  |
| ----------------------- | -------------------------- | ------------------------------------ |
| **Analysis depth**      | Surface-level              | Deep, context-rich                   |
| **Custom instructions** | ❌ Not applied             | ✅ Fully applied                     |
| **Diff size**           | Small changes only         | Entire diffs (1,500+ lines)          |
| **Security checks**     | Basic pattern matching     | Comprehensive vulnerability analysis |
| **Style checks**        | Default suggestions        | Team-specific standards              |
| **Output**              | Quick hints                | Full, aligned with team standards    |
| **Location**            | Basic GitHub.com checks    | PR reviews + IDE analysis            |

### Example Scenario: Massive Refactor

**Situation**: Developer pushes massive refactor touching dozens of files

**Without PRUs**:

```
Reviewer manually checks security →
Manually checks style →
Hours spent on repetitive checks →
Eventually spots issues
Time: Many hours
```

**With PRUs**:

```
Copilot assigned as reviewer →
Uses PRUs to apply security/style guidelines →
Scans entire change in seconds →
Flags unsafe string interpolations →
Drafts Markdown comments explaining issues
Time: Seconds
```

**Result**: Human reviewers focus on architectural impact, not manual checks

## Why PRUs Matter for Teams

### Three Key Benefits

| Benefit                    | What It Enables                                                 | Impact                                 |
| -------------------------- | --------------------------------------------------------------- | -------------------------------------- |
| **Deeper analysis**        | Spot subtle vulnerabilities, duplicated logic, style violations | Issues caught before production        |
| **Enforce consistency**    | Apply same security/readability/style checks automatically      | Uniform standards across all PRs       |
| **Handle activity bursts** | Rely on PRU reviews during busy release cycles                  | Maintain quality despite time pressure |

### Scalability in High-Volume Environments

**What PRUs enable**:

- ✅ Subtle vulnerability detection across large diffs
- ✅ Duplicated logic identification
- ✅ Style violation flagging
- ✅ Automated security checks
- ✅ Readability enforcement
- ✅ Quality maintenance during release cycles

**Human reviewers focus on**: Complex design decisions and architecture

### Example Scenario: Microservices Architecture

**Context**: Team maintains microservices in Go, Python, and TypeScript

**Situation**: Pre-release crunch with changes across all services

**PRU-powered review process**:

| Service          | Language   | What Copilot Flags                      | Fix                       |
| ---------------- | ---------- | --------------------------------------- | ------------------------- |
| **API Gateway**  | JavaScript | Risky `eval()` call                     | Recommend safer parser    |
| **Auth Service** | Go         | Missing error check in handler          | Add proper error handling |
| **Data Service** | Python     | SQL injection vulnerability             | Use parameterized queries |
| **Frontend**     | TypeScript | Unused imports and type inconsistencies | Clean imports, fix types  |

**Result**: Team merges fixes quickly across all services without missing critical details

**Without PRUs**: Team would need to manually review each service's language-specific best practices

## Measuring the Impact of PRU-Powered Reviews

### Three Key Metrics to Track

| Metric                   | What It Measures                         | Why It Matters                   |
| ------------------------ | ---------------------------------------- | -------------------------------- |
| **PR lead time**         | Time from PR open to merge               | Shows speed improvement          |
| **Quality indicators**   | Post-merge security/style issues flagged | Demonstrates quality improvement |
| **Developer experience** | Feedback on review speed and clarity     | Measures team satisfaction       |

### Metric 1: PR Lead Time

**Definition**: How quickly pull requests go from open to merged after adding Copilot reviews

**How to measure**:

- Track average days from PR open to merge
- Compare before and after Copilot reviews
- Focus on large PRs (500+ lines)

**Example metric**:

| Period                 | Large PR Merge Time | Follow-up Commits | Quality Issues |
| ---------------------- | ------------------- | ----------------- | -------------- |
| **Before PRU reviews** | 3 days average      | Frequent          | Many           |
| **After PRU reviews**  | 1 day average       | Rare              | Few            |

**Impact**: 67% reduction in merge time, fewer post-merge fixes

### Metric 2: Quality Indicators

**What to track**:

- Security issues found post-merge
- Style fixes needed after release
- Bugs discovered in production
- Regression rate

**Example measurement**:

```
Before PRUs: 15 style issues per month post-merge
After PRUs: 3 style issues per month post-merge
Improvement: 80% reduction
```

### Metric 3: Developer Experience

**How to gather feedback**:

- Quarterly surveys
- Review comment analysis
- Team retrospectives
- Time-to-value perception

**Questions to ask**:

- "Do Copilot reviews make PRs faster to merge?"
- "Are review comments clearer and more actionable?"
- "Do you feel more confident in merged code quality?"

## Optimizing PRU Usage

### Four Optimization Strategies

| Strategy                   | Action                                          | Benefit                     |
| -------------------------- | ----------------------------------------------- | --------------------------- |
| **Plan ahead**             | Set alerts at 75%, 90%, 100% of monthly PRUs    | Avoid unexpected exhaustion |
| **Use PRUs strategically** | Reserve for large/high-risk changes             | Maximum value per PRU       |
| **Refine prompts**         | Clean, specific requests                        | Reduce retries and waste    |
| **Scale up if needed**     | Consider higher-tier plan if consistently maxed | Support team workload       |

### Strategy 1: Plan Ahead (Usage Alerts)

**Setup alert thresholds**:

| Threshold | Action                                   | Example Response                   |
| --------- | ---------------------------------------- | ---------------------------------- |
| **75%**   | Monitor closely, evaluate usage patterns | Review which PRs consume most PRUs |
| **90%**   | Prioritize critical reviews only         | Defer non-urgent large PR reviews  |
| **100%**  | Emergency protocol, assess plan upgrade  | Fast-track plan upgrade discussion |

**How to set up**:

1. Access usage dashboard (organization settings)
2. Configure email alerts for thresholds
3. Assign ownership for monitoring
4. Document escalation procedures

### Strategy 2: Use PRUs Strategically

**Decision matrix**:

| Change Type                  | Size         | Risk Level | Use PRUs? | Why                       |
| ---------------------------- | ------------ | ---------- | --------- | ------------------------- |
| **Production code refactor** | 1,500+ lines | High       | ✅ Yes    | Large, high-risk changes  |
| **Security-sensitive code**  | Any size     | High       | ✅ Yes    | Security is critical      |
| **New feature**              | 500+ lines   | Medium     | ✅ Yes    | Significant code addition |
| **Documentation update**     | Any size     | Low        | ❌ No     | Low risk, non-code        |
| **Config change**            | Small        | Low        | ❌ No     | Simple, low impact        |
| **Typo fix**                 | 1-2 lines    | Low        | ❌ No     | Trivial change            |

**Reserve PRUs for**:

- Large changes (500+ lines)
- High-risk code (security, payments, auth)
- Production-impacting features
- Multi-file refactors
- Complex algorithm implementations

**Use lightweight reviews for**:

- Documentation updates
- Configuration tweaks
- Typo fixes
- Small bug fixes (<50 lines)
- Comment-only changes

### Strategy 3: Refine Your Prompts

**Poor prompts waste PRUs through retries**:

❌ **Vague**: "Check this code"
❌ **Too broad**: "Review everything for any issues"
❌ **Unclear**: "Make it better"

✅ **Good prompts are clean and specific**:

| Prompt Quality | Example                                                     | PRUs Used | Retries |
| -------------- | ----------------------------------------------------------- | --------- | ------- |
| ❌ **Poor**    | "Review this"                                               | 3-4       | 2-3     |
| ⚠️ **Okay**    | "Check for security issues"                                 | 2         | 1       |
| ✅ **Good**    | "Review for SQL injection vulnerabilities in database code" | 1         | 0       |

**Prompt optimization tips**:

- Be specific about what to check
- Reference relevant files/sections
- Mention applicable guidelines
- State expected output format
- Include context about change purpose

### Strategy 4: Scale Up If Needed

**When to consider upgrading**:

| Signal                        | What It Means                  | Action                      |
| ----------------------------- | ------------------------------ | --------------------------- |
| **Consistently maxed out**    | Hit 100% PRUs every month      | Evaluate higher-tier plan   |
| **Missing critical reviews**  | Can't review important PRs     | Urgent upgrade needed       |
| **Team growth**               | More developers = more reviews | Proactive capacity planning |
| **Quality metrics declining** | Can't maintain standards       | Increase PRU allocation     |

**Plan comparison**:

| Plan           | Monthly PRUs | Best For                   |
| -------------- | ------------ | -------------------------- |
| **Pro**        | Base         | Individual developers      |
| **Pro+**       | Enhanced     | Power users, high activity |
| **Business**   | Scaled       | Teams                      |
| **Enterprise** | Custom       | Large organizations        |

### Example Scenario: Documentation PRU Waste

**Problem discovered**: Team spends many PRUs on trivial documentation changes

**Analysis**:

```
Monthly PRU usage breakdown:
- Production code reviews: 40% (appropriate)
- Feature PRs: 35% (appropriate)
- Documentation changes: 25% (wasteful)
```

**Solution implemented**:

1. Update workflow guidelines
2. Use non-PRU lightweight reviews for docs
3. Reserve PRU reviews for code affecting production

**Result**:

```
New monthly PRU usage:
- Production code reviews: 55% (increased coverage)
- Feature PRs: 45% (increased coverage)
- Documentation changes: 0% (lightweight only)

Total PRU reduction: 30%
Quality maintained: Yes
```

## PRU Budget Management

### Monthly Planning

**Calculate expected usage**:

| Factor                   | Estimate Method                    | Example Calculation        |
| ------------------------ | ---------------------------------- | -------------------------- |
| **Team size**            | Developers × PRs per dev per month | 10 devs × 8 PRs = 80 PRs   |
| **Average PR size**      | Lines of code per PR               | 500 lines average          |
| **PRU per review**       | Based on PR size and complexity    | 2 PRUs per large PR        |
| **Monthly PRU estimate** | Large PRs × PRUs per review        | 40 large PRs × 2 = 80 PRUs |

### Cost-Benefit Analysis

**Calculate ROI**:

| Metric                    | Before Copilot | After Copilot | Improvement |
| ------------------------- | -------------- | ------------- | ----------- |
| **Review time per PR**    | 2 hours        | 30 minutes    | 75% faster  |
| **PRs per week**          | 20             | 20            | Same volume |
| **Review hours saved**    | -              | 30 hours/week | Significant |
| **Cost (PRUs)**           | $0             | ~$50/month    | Worth it    |
| **ROI** (at $100/hr rate) | -              | $3,000/month  | 60x return  |

## PRU Consumption Summary

### What Consumes PRUs

| Activity                           | PRU Cost | When It Applies                             |
| ---------------------------------- | -------- | ------------------------------------------- |
| **Large PR review**                | 1-3 PRUs | 500+ line changes                           |
| **IDE deep analysis**              | 1-2 PRUs | Pre-commit comprehensive review             |
| **Custom instruction application** | +1 PRU   | When `.github/copilot-instructions.md` used |
| **Security scanning**              | 1-3 PRUs | Comprehensive vulnerability checks          |
| **Multi-file refactor**            | 2-5 PRUs | Changes spanning many files                 |

### What Doesn't Consume PRUs

| Activity                | PRU Cost | Use This For                |
| ----------------------- | -------- | --------------------------- |
| **Small refactors**     | 0 PRUs   | Single-line changes         |
| **Inline suggestions**  | 0 PRUs   | Real-time code completion   |
| **Simple chat queries** | 0 PRUs   | Basic questions             |
| **Code explanations**   | 0 PRUs   | Understanding existing code |
| **Lightweight reviews** | 0 PRUs   | Small documentation changes |

## Best Practices Summary

### Strategic Usage

| Practice                       | How To Implement                             | Expected Impact                     |
| ------------------------------ | -------------------------------------------- | ----------------------------------- |
| **Prioritize high-impact PRs** | Review production code, skip trivial changes | 30-40% PRU savings                  |
| **Set usage alerts**           | Configure at 75%, 90%, 100%                  | Avoid unexpected exhaustion         |
| **Refine prompts**             | Be specific, avoid vague requests            | Reduce retries by 50%               |
| **Track metrics**              | Monitor lead time, quality, satisfaction     | Quantify ROI                        |
| **Regular audits**             | Monthly review of PRU consumption patterns   | Identify optimization opportunities |

### Team Adoption

| Phase        | Action                              | Timeline  |
| ------------ | ----------------------------------- | --------- |
| **Pilot**    | Start with 1-2 critical repos       | Month 1   |
| **Measure**  | Track lead time and quality metrics | Month 2-3 |
| **Optimize** | Refine usage based on data          | Month 4   |
| **Scale**    | Expand to more repos                | Month 5+  |

## Key Benefits of PRU-Powered Reviews

| Benefit                   | What You Get                           |
| ------------------------- | -------------------------------------- |
| **Deeper analysis**       | Catch subtle issues before production  |
| **Context-rich insights** | Aligned with your team's standards     |
| **Faster reviews**        | Seconds instead of hours               |
| **Consistent quality**    | Same standards across all PRs          |
| **Scalable reviews**      | Handle high-volume environments        |
| **Focus human reviewers** | On architecture, not repetitive checks |

## Quick Reference: PRU Optimization

**When to use PRUs**:

```
✅ Large PRs (500+ lines)
✅ Security-sensitive code
✅ Production-impacting features
✅ Multi-file refactors
✅ Complex implementations
```

**When to skip PRUs**:

```
❌ Documentation updates
❌ Typo fixes
❌ Config tweaks
❌ Comment-only changes
❌ Small bug fixes (<50 lines)
```

**Optimization checklist**:

```
□ Set alerts at 75%, 90%, 100%
□ Reserve PRUs for high-risk changes
□ Use specific, clear prompts
□ Track monthly consumption
□ Review patterns quarterly
□ Scale plan if consistently maxed
```

## Key Takeaways

✅ **PRUs unlock extra gear**: Enable Copilot's most powerful review features
✅ **Premium vs. lightweight**: PRUs for large/complex changes, lightweight for simple tasks
✅ **Three key benefits**: Deeper analysis, enforce consistency, handle activity bursts
✅ **Measure impact**: Track PR lead time, quality indicators, developer experience
✅ **Four optimization strategies**: Plan ahead (alerts), strategic usage, refine prompts, scale up
✅ **Example metrics**: 3 days → 1 day PR merge time (67% improvement)
✅ **Strategic usage**: Reserve PRUs for 500+ line changes, high-risk code, production features
✅ **Prompt refinement**: Clean, specific requests reduce retries and waste
✅ **Cost-benefit**: 30% PRU reduction possible with workflow optimization
✅ **Scale appropriately**: Upgrade plan if consistently maxed out
⚠️ **Human judgment essential**: PRUs enhance reviews, but humans make final decisions

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/code-reviews-pull-requests-github-copilot/5-impact-optimization-premium-request-units)

---

## Complete Module Summary

This module covered **4 major sections**:

1. ✅ **What GitHub Copilot adds to the review process** - 5 core features, PRU-powered reviews, 5 ways Copilot helps
2. ✅ **Using Copilot as a reviewer in GitHub.com** - 6-step process, customization, comment interaction
3. ✅ **Catching issues early and automating reviews** - Local IDE reviews, path-specific instructions, automation at 3 levels
4. ✅ **Measuring impact and optimizing PRUs** - Understanding PRUs, measuring impact, optimization strategies

**Total module length**: ~1,600 lines of comprehensive documentation
