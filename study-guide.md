# GH-300: GitHub Copilot Certification Study Guide

**Exam**: GitHub Copilot (GH-300)
**Target Audience**: Software developers, administrators, and project managers proficient in using GitHub
**Prerequisites**: Foundational understanding of GitHub Copilot and hands-on experience optimizing software development workflows

## 📊 Exam Structure Overview

| Domain                          | Weight | Focus Area                                    |
| ------------------------------- | ------ | --------------------------------------------- |
| **1. Responsible AI**           | 7%     | AI risks, limitations, ethical considerations |
| **2. Copilot Plans & Features** | 31%    | Plans, features, Chat, Enterprise, CLI        |
| **3. Data Handling**            | 15%    | Data pipeline, context, limitations           |
| **4. Prompt Engineering**       | 9%     | Crafting, context, best practices             |
| **5. Developer Use Cases**      | 14%    | Productivity, SDLC, limitations               |
| **6. Testing**                  | 9%     | Test generation, edge cases, SKUs             |
| **7. Privacy & Exclusions**     | 15%    | Content exclusions, security, troubleshooting |

**Total**: 100%

### Exam Format

- **Total Questions**: 65 questions
- **Question Format**: Many questions require selecting **2 out of 4 options** - read carefully!
- **Topics appear across domains**: While specific topics may be weighted, content from all curriculum areas appears throughout the exam

📚 **Real Exam Experience**: See [Exam Experience Document](exam-experience.md) for specific topics that appeared frequently and tricky areas to focus on.

---

## 🎯 Domain 1: Responsible AI (7%)

### Topics Covered

- Risks associated with AI (bias, security, fairness, privacy)
- Limitations of generative AI tools
- Validating AI outputs
- Operating responsible AI systems
- Mitigating potential harms
- Ethical AI principles

### Study Resources

📚 **Main Module**: [Responsible AI with GitHub Copilot](Fundamentals_Part_1/1_Responsible_AI_with_GIthub_Copilot.md)

### Key Concepts to Master

**Six Principles of Responsible AI**:

1. **Fairness** - Treat all people fairly; detect/mitigate bias
2. **Reliability & Safety** - Operate consistently; minimize harm
3. **Privacy & Security** - User consent, encryption, access control
4. **Inclusiveness** - Empower everyone
5. **Transparency** - Understandable systems
6. **Accountability** - Monitor performance, take responsibility

**Key Risks**:

- Hard to interpret AI decisions
- Bias in training data
- Privacy violations
- Unintended harm
- Security vulnerabilities in generated code

**Mitigation Strategies**:

- Governance frameworks
- Transparency in operations
- Human oversight
- Regular validation of outputs
- Code review processes

### Exam Tips

✅ Understand the difference between **risks** and **limitations**
✅ Know how to **mitigate each risk** with specific strategies
✅ Be able to explain **why validation is necessary**
✅ Memorize the **six principles** and their applications

---

## 🎯 Domain 2: GitHub Copilot Plans & Features (31%)

**HIGHEST WEIGHT - Focus heavily on this domain!**

### Topics Covered

#### Plans & Differences

- Copilot Individual vs Business vs Enterprise
- Features by plan
- Billing and subscription management
- Data exclusions and IP indemnity

#### IDE Features

- GitHub Copilot in the IDE
- GitHub Copilot Chat in the IDE
- Triggering methods (chat, inline chat, suggestions, CLI)

#### Business Features

- Content exclusions
- Organization-wide policies
- Audit logs
- REST API management - Usage metrics endpoints at enterprise/org/team levels
- Public code detection - Matching public code settings (Block/Allow)

#### Chat Features

- Use cases and best practices
- Performance optimization
- Limitations
- Code suggestions options
- Slash commands
- Feedback mechanisms

#### Enterprise Features

- GitHub Copilot Chat on GitHub.com
- PR summaries
- Knowledge Bases (creation, management, indexing)
- Custom models

#### CLI Features

- Installation steps
- Common commands - `gh copilot explain`, `gh copilot suggest`, `gh copilot alias`, `gh copilot config`
- Configuration settings
- Issue assignment - `gh issue edit --add-assignee copilot`
- Shell alias setup (`ghcs` for direct execution)

### Study Resources

📚 **Core Modules**:

- [Introduction to GitHub Copilot](Fundamentals_Part_1/2_Introduction_to_Github_Copilot.md)
- [Advanced Features](Fundamentals_Part_1/5_Using_advanced_Github_Copilot_Features.md)
- [Copilot Across Environments](Fundamentals_Part_1/6_Github_Copilot_Across_Envs_IDE_Chat_Github.com_CLI.md)
- [Management & Customization](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md)

📋 **Quick References**:

- [Subscription Plans](Quick_Reference/subscription-plans.md)
- [Commands](Quick_Reference/commands.md)
- [When to Use What](Quick_Reference/when-to-use-what.md)
- [Copilot Across Platforms](Quick_Reference/copilot-across-platforms.md)

### Key Concepts to Master

#### Plan Comparison

| Feature                | Free/Pro              | Business | Enterprise |
| ---------------------- | --------------------- | -------- | ---------- |
| **Completions**        | 2000 (Free) / ∞ (Pro) | ∞        | ∞          |
| **Chat**               | 50 (Free) / ∞ (Pro)   | ∞        | ∞          |
| **IP Indemnity**       | ❌                    | ✅       | ✅         |
| **Content Exclusions** | ❌                    | ✅       | ✅         |
| **Audit Logs**         | ❌                    | ✅       | ✅         |
| **Knowledge Bases**    | ❌                    | ❌       | ✅         |
| **Custom Models**      | ❌                    | ❌       | ✅         |

#### Triggering Copilot (5 Methods)

1. **Inline suggestions** - Auto-appears as you type
2. **Inline Chat** - `Ctrl+I` / `Cmd+I`
3. **Chat view** - Click chat icon
4. **Right-click menus** - Context actions
5. **CLI** - `gh copilot suggest/explain`

#### Essential Slash Commands

| Command           | Purpose              | Use Case                      |
| ----------------- | -------------------- | ----------------------------- |
| `/fix`            | Fix bugs             | Select buggy code, run `/fix` |
| `/explain`        | Explain code         | Understand complex logic      |
| `/tests`          | Generate tests       | Create unit tests             |
| `/doc`            | Add documentation    | Generate comments             |
| `/optimize`       | Improve performance  | Enhance efficiency            |
| `/setupTests`     | Setup test framework | Configure testing             |
| `/fixTestFailure` | Fix failing tests    | Debug test issues             |

#### Content Exclusions

**Configuration Levels**:

**Repository Level**:

1. Repo main page → **Settings**
2. Code & automation → **Copilot** → **Content exclusion**
3. In "Paths to exclude in this repository" box, specify paths
   - Format: `"/PATH/TO/DIRECTORY/OR/FILE"` (one per line)
   - Supports wildcard patterns (e.g., `"**/.env"`, `"**/.env.*"`)

**Organization Level**:

1. Profile → **Your organizations** → **Settings**
2. **Copilot** → **Content exclusion**
3. Enter files/repos to exclude

**Important**:

- ❌ **`.gitignore` does NOT affect Copilot** - `.gitignore` only affects Git tracking
- ✅ File-level exclusion is done by **specifying paths** in settings (not via a file in the repo)

**Effects**:

- ❌ No completions in excluded files
- ❌ Content won't inform other suggestions
- ❌ Content won't inform Chat responses

**Availability**: **Business and Enterprise plans only**

**Limitations**:

- Takes up to 30 minutes to apply (reload IDE for immediate effect)
- May not apply in Chat with `@github` participant
- Only applies to org members
- Copilot may use type info from excluded files if referenced in non-excluded files

#### Knowledge Bases (Enterprise Only)

**Important**: Knowledge Bases are **Enterprise plan ONLY** - not available on Free, Pro, Pro+, or Business plans

**Types of Knowledge**:

- Code snippets
- Best practices
- Design patterns
- API documentation
- Coding standards

**Benefits**:

- Improved code quality
- Consistency across team
- Efficient code completion
- Better code reviews
- Attach knowledge bases to tailor chat responses
- Custom model training on internal codebase
- Codebase indexing

#### Public Code Detection / Duplicate Detection Filter

**Setting Location**: Organization/Enterprise Settings → Copilot → Under Suggestions → **Matching public code**

**Options**: **Block** or **Allow**

**Purpose**: Filters out suggestions that match public code to minimize overlap and reduce risk

**IP Indemnity Requirement**: Must be set to **Block** for IP indemnity protection (Business & Enterprise plans)

**Availability**: Available on **all plans** (Free, Pro, Business, Enterprise)

**Steps to Configure**:

1. Profile photo → Your enterprises/organizations
2. Next to enterprise/org → **Settings**
3. Left sidebar → **Copilot**
4. Under Suggestions → Matching public code → **Block** or **Allow**
5. **Save**

### Exam Tips

✅ **Memorize plan features** - This is heavily tested
✅ **Know all slash commands** and their use cases
✅ **Understand content exclusions** - setup, effects, limitations
✅ **CLI commands** - installation and usage, including `gh copilot explain`, `gh copilot suggest`, `gh copilot config`, `gh copilot alias`
✅ **REST API** - Usage metrics API endpoints for enterprises, organizations, and teams
✅ **GraphQL API** - For assigning issues to Copilot programmatically
✅ **Public code detection** - How to enable/disable settings
✅ **Content exclusions** - Configuration steps at repository and organization levels
✅ **Knowledge Bases** - **Enterprise ONLY** - creation, management, benefits
✅ **Feature availability** - What works in IDE vs GitHub.com vs CLI

---

## 🎯 Domain 3: How GitHub Copilot Works & Handles Data (15%)

### Topics Covered

#### Data Pipeline Lifecycle

- Lifecycle of code suggestions
- Context gathering
- Prompt building
- Proxy service and filters
- LLM response generation
- Post-processing
- Matching code identification

#### Data Handling

- Data usage and sharing (Individual plan)
- Code completion data flow
- Chat data flow
- Input processing types

#### Limitations

- Most-seen examples effect
- Age of code suggestions
- Reasoning vs calculations
- Limited context windows

### Study Resources

📚 **Core Modules**:

- [Prompt Engineering](Fundamentals_Part_1/3_Introduction_to_Prompt_Engineering_with_Github_Copilot.md)
- [Developer Use Cases](Fundamentals_Part_1/8_Developer_use_cases_for_AI_with_Github_Copilot.md)

📋 **Quick Reference**: [Prompt Engineering Cheatsheet](Quick_Reference/prompt-engineering-cheatsheet.md)

### Key Concepts to Master

#### Data Pipeline Flow

**Inbound**:

```
User Input → HTTPS → Context Gathering →
Proxy Filter → Toxicity Filter → LLM Generation
```

**Outbound**:

```
LLM Response → Post-processing → Validation →
Security Check → Public Code Match → Delivery → Feedback
```

#### Context Gathering

Copilot gathers context from:

- Current file content
- Open tabs in IDE
- File type and language
- Comments and docstrings
- Function/class names
- Recent edits

#### Data Retention

| Feature                   | Retention    | Purpose                        |
| ------------------------- | ------------ | ------------------------------ |
| **Code Suggestions**      | Not retained | Prompts discarded after use    |
| **Chat (outside editor)** | 28 days      | Enable follow-up conversations |
| **Chat (in editor)**      | Session only | Temporary context              |

#### Context Windows

- **Standard suggestions**: 200-500 lines
- **Chat**: 4,000 tokens
- **Workspace queries**: Larger context (varies)

#### Limitations of LLMs

1. **Most-seen examples bias** - Common patterns over-represented
2. **Age of training data** - May not include latest features
3. **Reasoning vs calculations** - Better at patterns than math
4. **Context window limits** - Can't process entire large codebases at once

### Exam Tips

✅ **Visualize the pipeline** - Know each step
✅ **Understand data retention** - What's kept vs. discarded
✅ **Context gathering** - How Copilot builds prompts
✅ **Filters** - Proxy, toxicity, post-processing
✅ **Limitations** - Be able to explain each one

---

## 🎯 Domain 4: Prompt Crafting & Engineering (9%)

### Topics Covered

#### Prompt Crafting Fundamentals

- Context determination
- Language options
- Parts of a prompt
- Role of prompting
- Zero-shot vs few-shot prompting
- Chat history usage
- Best practices

#### Prompt Engineering

- Principles and methods
- Training approaches
- Best practices
- Process flow

### Study Resources

📚 **Core Module**: [Prompt Engineering with GitHub Copilot](Fundamentals_Part_1/3_Introduction_to_Prompt_Engineering_with_Github_Copilot.md)

📋 **Quick Reference**: [Prompt Engineering Cheatsheet](Quick_Reference/prompt-engineering-cheatsheet.md)

### Key Concepts to Master

#### The 4 Ss Framework

| Principle    | Meaning                             |
| ------------ | ----------------------------------- |
| **Single**   | Focus on one well-defined task      |
| **Specific** | Use explicit, detailed instructions |
| **Short**    | Keep prompts concise                |
| **Surround** | Provide context via open files      |

#### Learning Approaches

| Approach      | Description       | Best For          |
| ------------- | ----------------- | ----------------- |
| **Zero-shot** | No examples       | Common patterns   |
| **One-shot**  | Single example    | Consistency       |
| **Few-shot**  | Multiple examples | Complex scenarios |

#### Prompt Engineering Techniques

**Role Prompting**:

```
Act as a cybersecurity expert. Create a password validation function
following OWASP guidelines...
```

**Chain Prompting**:

- Summarize context instead of repeating
- Build on previous responses
- Manage long conversations efficiently

**Context Management**:

- `#file:` - Reference specific files
- `@workspace` - Workspace-wide context
- `@terminal` - CLI context

#### Parts of a Prompt

1. **Task description** - What you want
2. **Context** - Relevant information
3. **Constraints** - Limitations or requirements
4. **Examples** (optional) - Show desired pattern
5. **Format** (optional) - Expected output structure

### Exam Tips

✅ **Memorize the 4 Ss** - This is fundamental
✅ **Know the difference** between zero-shot, one-shot, few-shot
✅ **Role prompting examples** - Security, performance, testing
✅ **Context agents** - `@workspace`, `@terminal`, `@file`
✅ **Best practices** - Clear, explicit, with examples

---

## 🎯 Domain 5: Developer Use Cases for AI (14%)

### Topics Covered

#### Productivity Improvements

- Learning new languages/frameworks
- Language translation
- Context switching
- Writing documentation
- Personalized responses
- Sample data generation
- Modernizing legacy apps
- Debugging
- Data science
- Code refactoring

#### SDLC Integration

- How Copilot helps across SDLC phases
- Workflow optimization

#### Limitations

- Understanding constraints
- When NOT to use Copilot

#### Measuring Impact

- Productivity API
- Usage metrics
- ROI calculation

### Study Resources

📚 **Core Modules**:

- [Developer Use Cases](Fundamentals_Part_1/8_Developer_use_cases_for_AI_with_Github_Copilot.md)
- [Agent Mode](Fundamentals_Part_2/1_Building_applications_with_Github_Copilot_agent_mode.md)
- [Coding Agent](Fundamentals_Part_2/2_Accelerate_development_with_Github_Copilot_coding_agent.md)

📋 **Quick References**:

- [Agent Mode vs Coding Agent](Quick_Reference/agent-mode-vs-coding-agent.md)
- [When to Use What](Quick_Reference/when-to-use-what.md)

### Key Concepts to Master

#### SDLC Phases

| Phase                    | How Copilot Helps                                 |
| ------------------------ | ------------------------------------------------- |
| **Requirements**         | Rapid prototyping, user story → code, API design  |
| **Design & Development** | Boilerplate, design patterns, optimization        |
| **Testing & QA**         | Unit tests, test data, edge cases, assertions     |
| **Deployment**           | Config files, deployment scripts, documentation   |
| **Maintenance**          | Bug fixes, refactoring, legacy code understanding |

#### Common Use Cases

**Learning**:

- Context-aware snippets for unfamiliar languages
- API usage examples
- Inline documentation

**Automation**:

- Boilerplate code generation (2-5 PRUs for complex)
- Sample data creation
- Test suite generation

**Documentation**:

- Inline comments
- Function descriptions
- README generation

#### Agent Mode vs Coding Agent

| Feature        | Agent Mode (IDE) | Coding Agent (GitHub) |
| -------------- | ---------------- | --------------------- |
| **Location**   | Local IDE        | GitHub Actions        |
| **Output**     | Direct edits     | Pull requests         |
| **Visibility** | Local            | Team-visible          |
| **PRU cost**   | 2-5 PRUs         | 1 PRU per request     |

#### Productivity Metrics

**REST API Endpoints**:

- `GET /enterprises/{enterprise}/copilot/usage`
- `GET /enterprises/{enterprise}/team/{team_slug}/copilot/usage`
- `GET /orgs/{org}/copilot/usage`

**Metrics Provided**:

- Suggestions and acceptances
- Active users
- Breakdown by editor and language
- Completions and chat interactions

**Measurement Framework**:

1. **Evaluation** - Developer satisfaction, task completion
2. **Adoption** - Productivity metrics, enablement
3. **Optimization** - Time-to-market, code quality
4. **Sustained Efficiency** - Long-term gains

### Exam Tips

✅ **Know SDLC phases** and Copilot's role in each
✅ **Common use cases** - Be able to explain 5-7 examples
✅ **Agent Mode vs Coding Agent** - Key differences
✅ **Productivity API** - Endpoints and metrics
✅ **Limitations** - When NOT to rely on Copilot
✅ **Measurement framework** - Four stages

---

## 🎯 Domain 6: Testing with GitHub Copilot (9%)

### Topics Covered

#### Test Generation

- Unit tests
- Integration tests
- Other test types
- Edge cases identification

#### SKUs & Configuration

- Different SKUs and privacy
- Code suggestion configurations (org level)
- Editor config file

### Study Resources

📚 **Core Module**: [Develop Unit Tests](Fundamentals_Part_1/9_Develop_Unit_Tests_using_Github_Copilot_Tools.md)

📋 **Quick Reference**: [Testing Quick Guide](Quick_Reference/testing-quick-guide.md)

### Key Concepts to Master

#### Four Ways to Generate Tests

| Method               | When to Use          | How                                   |
| -------------------- | -------------------- | ------------------------------------- |
| **Chat view**        | Project/class/method | Ask/Edit/Agent mode                   |
| **Inline Chat**      | Selected code        | Select → `Ctrl+I` → `/tests`          |
| **Smart action**     | Fastest way          | Right-click → "Generate Tests"        |
| **Code completions** | Add more tests       | Type in test file, accept suggestions |

#### Testing Slash Commands

| Command           | Purpose                  |
| ----------------- | ------------------------ |
| `/setupTests`     | Configure test framework |
| `/tests`          | Generate unit tests      |
| `/fixTestFailure` | Fix failing tests        |

#### C# Test Frameworks

Supported frameworks:

- **xUnit** - `.NET:New Project...` → xUnit Test Project
- **NUnit** - `.NET:New Project...` → NUnit3 Test Project
- **MSTest** - `.NET:New Project...` → MSTest Test Project

**Requirements**:

- .NET 8.0+ SDK
- C# Dev Kit extension
- Test framework package

#### Test Explorer Features

| Feature          | How to Access                     |
| ---------------- | --------------------------------- |
| **Open**         | Click beaker icon on Activity bar |
| **Run test**     | Green play button next to test    |
| **Debug**        | Right-click → Debug               |
| **View results** | Automatic update in explorer      |
| **Fix failure**  | Hover → Sparkle icon              |

#### Agent Mode for Testing

**Automated workflow**:

```
Agent Mode → Scaffold test project → Create test file →
Generate tests → Run tests → Fix failures → Report
```

**PRU Usage**: 2-5 PRUs for comprehensive test generation

#### SKUs & Privacy Considerations

| Plan           | Privacy Features                                |
| -------------- | ----------------------------------------------- |
| **Free/Pro**   | Basic (data not excluded from training)         |
| **Business**   | Data excluded, IP indemnity, content exclusions |
| **Enterprise** | All Business + custom models, knowledge bases   |

#### Organization-Level Configuration

**Code Suggestion Options**:

- Enable/disable for repos
- Content exclusions
- Matching public code blocking
- Suggestion collection settings

**Editor Config File**: `.github/copilot-instructions.md`

- Define testing standards
- Specify frameworks
- Set naming conventions
- Request specific patterns

### Exam Tips

✅ **Four methods** - Know when to use each
✅ **Slash commands** - Testing-specific commands
✅ **Test frameworks** - Setup steps for xUnit, NUnit, MSTest
✅ **Test Explorer** - Features and usage
✅ **Agent Mode** - Automated testing workflow
✅ **SKU differences** - Privacy features by plan
✅ **Org configuration** - Content exclusions, settings

---

## 🎯 Domain 7: Privacy Fundamentals & Context Exclusions (15%)

### Topics Covered

#### Code Quality Through Testing

- Improving existing tests
- Boilerplate generation
- Writing assertions

#### Security & Performance

- Learning from tests
- Collaborative reviews (Enterprise)
- Security vulnerability identification
- Code optimizations

#### Content Exclusions

- Configuration (repo & org level)
- Effects and limitations
- Output ownership

#### Safeguards

- Duplication detector filter
- Contractual protection
- Settings on GitHub.com
- Duplication detection toggle
- Prompt/suggestion collection toggle
- Security checks and warnings

#### Troubleshooting

- Missing code suggestions
- Context exclusions not applied
- Triggering Copilot
- Context exclusion steps in editors

### Study Resources

📚 **Core Modules**:

- [Management & Customization](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md)
- [Code Reviews](Fundamentals_Part_2/4_Leveling_up_code_reviews_and_pull_requests_with_Github_Copilot.md)

📋 **Quick References**:

- [Troubleshooting](Quick_Reference/troubleshooting.md)
- [Code Review Quick Guide](Quick_Reference/code-review-quick-guide.md)

### Key Concepts to Master

#### Content Exclusions Setup

**Repository Level**:

```
Repo → Settings → Code & automation → Copilot →
Specify paths to exclude
```

**Organization Level**:

```
Profile → Your organizations → Settings →
Copilot → Content exclusion → Enter files/repos
```

#### Effects of Content Exclusions

When you exclude content:

- ❌ No completions in excluded files
- ❌ Content won't inform other suggestions
- ❌ Content won't inform Chat responses

#### Limitations of Content Exclusions

| Limitation          | Impact                                    |
| ------------------- | ----------------------------------------- |
| **IDE limitations** | May not apply in Chat with `@github`      |
| **Semantic info**   | Type info may leak via non-excluded files |
| **Policy scope**    | Only applies to org members               |
| **Delay**           | Takes up to 30 minutes to apply           |

#### Contractual Protection (IP Indemnity)

**Available**: Business & Enterprise plans

**Requirement**: "Matching public code" setting must be **blocked**

**Coverage**: GitHub assumes legal responsibility for IP infringement

#### Duplication Detector Filter

**Purpose**: Identifies code matching public repositories

**Configuration**:

```
Settings → Copilot → Suggestions matching public code →
Block / Allow
```

**Effect**: When blocked, filters out suggestions matching public code

#### GitHub.com Settings

**Duplication Detection**:

- Settings → Copilot → Matching public code → Block/Allow

**Prompt/Suggestion Collection**:

- Settings → Copilot → Data collection
- Enable/disable prompt collection
- Enable/disable suggestion collection

#### Security Checks

Copilot Code Review checks for:

- **Security**: Unsafe `eval()`, `exec()`, SQL injection
- **Type hints**: Missing parameter types
- **Formatting**: Inconsistent style
- **Bugs**: Logic errors, edge cases
- **Best practices**: Non-idiomatic patterns

#### Troubleshooting Common Issues

**No Code Suggestions**:

| Check             | Fix                          |
| ----------------- | ---------------------------- |
| **Internet**      | Verify connection (required) |
| **Extension**     | Update to latest version     |
| **Compatibility** | Check IDE configuration      |
| **Exclusions**    | Check status bar icon        |
| **Enabled**       | Click icon → Enable          |

**Content Exclusions Not Working**:

| Issue               | Solution                            |
| ------------------- | ----------------------------------- |
| **Just configured** | Wait 30 mins OR reload IDE          |
| **Not sure**        | Hover icon - diagonal line = active |
| **Chat working**    | Expected - some features bypass     |
| **Wrong scope**     | Only applies to org members         |

**Verification**:

```
Status bar icon with diagonal line (⊘) = File excluded
Normal icon = File included
```

**Triggering Copilot Manually**:

- `Ctrl+Enter` (VS Code) - Force suggestion
- Write more detailed comments
- Add examples in comments
- Reword prompt
- Cycle suggestions with `Alt+]` / `Option+]`

#### Code Review Automation

**Three Levels**:

1. **Account** (Pro/Pro+) - All your PRs
2. **Repository** - Single repo (any plan)
3. **Organization** - Multiple repos (any plan)

**Custom Instructions**: `.github/copilot-instructions.md`

- Team standards
- Security guidelines
- Style preferences
- Performance considerations

**Path-Specific**: `.github/instructions/*.instructions.md`

- Apply to specific file patterns
- Example: `**/*.py`, `src/**/*.ts`

### Exam Tips

✅ **Content exclusions** - Setup, effects, limitations (heavily tested)
✅ **IP indemnity** - Requirements and coverage
✅ **Duplication detector** - How it works, configuration
✅ **Troubleshooting** - Common issues and solutions
✅ **Settings locations** - Repo vs org vs account
✅ **Security checks** - What Copilot reviews for
✅ **Custom instructions** - Purpose and configuration
✅ **Verification methods** - Status bar icons, testing

---

## 📝 Study Plan Recommendations

### 4-Week Study Plan

#### Week 1: Foundations (Domains 1-2)

- **Day 1-2**: Responsible AI principles
- **Day 3-5**: Plan differences, features by SKU
- **Day 6-7**: IDE features, Chat, slash commands

**Practice**: Set up Copilot in IDE, try all slash commands

#### Week 2: Technical Deep Dive (Domains 3-4)

- **Day 1-3**: Data pipeline, context gathering, LLM flow
- **Day 4-5**: Prompt crafting (4 Ss framework)
- **Day 6-7**: Prompt engineering techniques

**Practice**: Create prompts using zero-shot, one-shot, few-shot approaches

#### Week 3: Practical Application (Domains 5-6)

- **Day 1-3**: Developer use cases, SDLC integration
- **Day 4-5**: Agent Mode vs Coding Agent
- **Day 6-7**: Testing features, all methods

**Practice**: Generate tests using all four methods, try Agent Mode

#### Week 4: Privacy & Review (Domain 7 + Review)

- **Day 1-2**: Content exclusions, safeguards
- **Day 3-4**: Security, troubleshooting
- **Day 5-7**: Full review, practice scenarios

**Practice**: Configure content exclusions, troubleshoot issues

### Study Strategies

#### High-Yield Topics (Focus Here)

Based on domain weights:

1. **Domain 2 (31%)** - Plans & Features

   - ⚡ Plan comparison tables
   - ⚡ Slash commands
   - ⚡ Content exclusions
   - ⚡ Knowledge Bases (Enterprise)

2. **Domain 7 (15%)** - Privacy & Exclusions

   - ⚡ Content exclusion setup
   - ⚡ Effects and limitations
   - ⚡ Troubleshooting

3. **Domain 3 (15%)** - Data Handling

   - ⚡ Data pipeline flow
   - ⚡ Context gathering
   - ⚡ Limitations

4. **Domain 5 (14%)** - Use Cases
   - ⚡ SDLC integration
   - ⚡ Productivity metrics
   - ⚡ Agent Mode vs Coding Agent

#### Hands-On Practice

**Essential Exercises**:

1. **Configure all three content exclusion levels**

   - Account
   - Repository
   - Organization

2. **Try all test generation methods**

   - Smart action
   - Inline Chat
   - Chat view (Ask, Edit, Agent modes)
   - Code completions

3. **Use all slash commands**

   - `/fix`, `/explain`, `/tests`, `/doc`
   - `/optimize`, `/setupTests`, `/fixTestFailure`

4. **Set up automatic code reviews**

   - Account-level (if Pro/Pro+)
   - Repository-level with rulesets
   - Create custom instructions

5. **Practice prompt engineering**
   - Zero-shot examples
   - One-shot examples
   - Few-shot examples
   - Role prompting

#### Memorization Aids

**Acronyms**:

- **4 Ss**: Single, Specific, Short, Surround
- **FRPITA**: Fairness, Reliability, Privacy, Inclusiveness, Transparency, Accountability

**Comparison Tables**:

- Plan features (Free vs Pro vs Business vs Enterprise)
- Agent Mode vs Coding Agent
- Test generation methods

**Process Flows**:

- Data pipeline (Inbound → Outbound)
- SDLC phases and Copilot's role
- Content exclusion setup

### Quick Reference Cards

Create flashcards for:

- [ ] All slash commands and their purposes
- [ ] Plan feature comparison
- [ ] PRU costs by feature
- [ ] Content exclusion effects and limitations
- [ ] Testing frameworks and setup commands
- [ ] Troubleshooting checklist
- [ ] Data retention policies
- [ ] Security checks Copilot performs

---

## 🎓 Exam Day Tips

### Before the Exam

✅ **Review Quick Reference Guides**

- [Commands](Quick_Reference/commands.md)
- [Subscription Plans](Quick_Reference/subscription-plans.md)
- [When to Use What](Quick_Reference/when-to-use-what.md)
- [Troubleshooting](Quick_Reference/troubleshooting.md)

✅ **Verify Your Knowledge**

- Can you explain the 6 principles of Responsible AI?
- Can you describe the data pipeline flow?
- Do you know all slash commands?
- Can you differentiate all plans?
- Can you set up content exclusions?

✅ **Practice Scenarios**

- Walk through test generation (all 4 methods)
- Explain Agent Mode vs Coding Agent
- Troubleshoot "no suggestions" issue
- Set up automatic code reviews

### During the Exam

**Time Management**:

- **65 questions** in ~120 minutes
- ~1.8 minutes per question
- Flag difficult questions, return later
- Focus on high-weight domains first (Domain 2 = 31%)

**Question Strategy**:

- Read carefully - watch for "NOT", "EXCEPT", "Select 2" (many questions require selecting multiple answers)
- Eliminate obviously wrong answers
- Domain 2 (31%) has most questions - be prepared
- Practical scenarios test real-world application

**Common Question Types**:

1. **Feature comparison** - "Which plan includes...?"
2. **Configuration** - "How do you set up...?"
3. **CLI commands** - "What command would you use to...?"
4. **API endpoints** - "Which API endpoint returns...?"
5. **Feature availability** - "What can Copilot do in IDEs vs GitHub.com?"
6. **Troubleshooting** - "If X happens, what should you check?"
7. **Best practices** - "What is the recommended way to...?"
8. **Limitations** - "What is NOT possible with...?"

---

## 📚 All Study Resources

### Fundamentals Part 1

1. [Responsible AI](Fundamentals_Part_1/1_Responsible_AI_with_GIthub_Copilot.md)
2. [Introduction to GitHub Copilot](Fundamentals_Part_1/2_Introduction_to_Github_Copilot.md)
3. [Prompt Engineering](Fundamentals_Part_1/3_Introduction_to_Prompt_Engineering_with_Github_Copilot.md)
4. [Copilot Spaces](Fundamentals_Part_1/4_Introduction_to_Copilot_Spaces.md)
5. [Advanced Features](Fundamentals_Part_1/5_Using_advanced_Github_Copilot_Features.md)
6. [Copilot Across Environments](Fundamentals_Part_1/6_Github_Copilot_Across_Envs_IDE_Chat_Github.com_CLI.md)
7. [Management & Customization](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md)
8. [Developer Use Cases](Fundamentals_Part_1/8_Developer_use_cases_for_AI_with_Github_Copilot.md)
9. [Develop Unit Tests](Fundamentals_Part_1/9_Develop_Unit_Tests_using_Github_Copilot_Tools.md)

### Fundamentals Part 2

1. [Building with Agent Mode](Fundamentals_Part_2/1_Building_applications_with_Github_Copilot_agent_mode.md)
2. [Coding Agent](Fundamentals_Part_2/2_Accelerate_development_with_Github_Copilot_coding_agent.md)
3. [MCP Server](Fundamentals_Part_2/3_Introduction_to_MCP_Server.md)
4. [Code Reviews & PRs](Fundamentals_Part_2/4_Leveling_up_code_reviews_and_pull_requests_with_Github_Copilot.md)
5. [Using with JavaScript](Fundamentals_Part_2/5_Using_Github_Copilot_with_Javascript.md)
6. [Using with Python](Fundamentals_Part_2/6_Using_Github_Copilot_with_Python.md)

### Quick Reference Guides

1. [Commands](Quick_Reference/commands.md)
2. [Copilot Across Platforms](Quick_Reference/copilot-across-platforms.md)
3. [Copilot Spaces](Quick_Reference/copilot-spaces-quick-guide.md)
4. [Prompt Engineering](Quick_Reference/prompt-engineering-cheatsheet.md)
5. [Subscription Plans](Quick_Reference/subscription-plans.md)
6. [Testing](Quick_Reference/testing-quick-guide.md)
7. [Troubleshooting](Quick_Reference/troubleshooting.md)
8. [When to Use What](Quick_Reference/when-to-use-what.md)
9. [Agent Mode vs Coding Agent](Quick_Reference/agent-mode-vs-coding-agent.md)
10. [MCP Server Setup](Quick_Reference/mcp-server-quick-setup.md)
11. [PRU Optimization](Quick_Reference/pru-optimization-guide.md)
12. [Code Review Guide](Quick_Reference/code-review-quick-guide.md)

---

## ✅ Pre-Exam Checklist

**Knowledge Verification**:

- [ ] Can explain all 6 Responsible AI principles
- [ ] Know features of Free, Pro, Business, Enterprise plans
- [ ] Can describe data pipeline (inbound → outbound)
- [ ] Understand the 4 Ss of prompt crafting
- [ ] Know difference between zero-shot, one-shot, few-shot
- [ ] Can explain SDLC integration points
- [ ] Understand Agent Mode vs Coding Agent
- [ ] Know all slash commands (8 total)
- [ ] Can set up content exclusions (3 levels)
- [ ] Understand IP indemnity requirements
- [ ] Know test generation methods (4 total)
- [ ] Can troubleshoot common issues
- [ ] Understand PRU consumption by feature
- [ ] Know security checks Copilot performs
- [ ] Can explain Knowledge Bases (Enterprise)

**Hands-On Verification**:

- [ ] Used Copilot in IDE for 2+ weeks
- [ ] Tried all slash commands
- [ ] Generated tests using all 4 methods
- [ ] Set up content exclusions
- [ ] Used Agent Mode for multi-file edits
- [ ] Configured automatic code reviews
- [ ] Created custom instructions file
- [ ] Troubleshot missing suggestions issue
- [ ] Used CLI commands (`gh copilot explain`, `gh copilot suggest`, `gh copilot config`, `gh copilot alias`)
- [ ] Reviewed PR with Copilot
- [ ] Configured public code detection settings
- [ ] Know API endpoints for usage metrics

**Study Resources Reviewed**:

- [ ] All Fundamentals Part 1 modules
- [ ] All Fundamentals Part 2 modules
- [ ] All Quick Reference guides
- [ ] This study guide (all domains)
- [ ] **[Exam Experience Document](exam-experience.md)** - Real exam insights and frequently tested topics
- [ ] Microsoft Learn modules (if available)
- [ ] Practice assessment (if available)

---

## 🎯 Final Preparation

### Day Before Exam

1. **Light review only** - Don't cram
2. **Focus on Quick References** - High-yield summaries
3. **Review [Exam Experience Document](exam-experience.md)** - Pay special attention to CLI commands, APIs, and configuration steps
4. **Review comparison tables** - Plans, features, methods
5. **Memorize CLI commands** - `gh copilot explain`, `gh copilot suggest`, `gh copilot config`, `gh copilot alias`
6. **Review API endpoints** - Usage metrics endpoints
7. **Get good sleep** - Critical for recall

### Exam Day

1. **Arrive early** (if in-person)
2. **Read questions carefully** - Watch for "NOT", "EXCEPT", **"Select 2"** - Many questions require choosing 2 out of 4 options!
3. **Take your time** - You have ~1.8 minutes per question (65 questions total)
4. **Use process of elimination** - Rule out wrong answers
5. **Flag and return** - Don't get stuck
6. **Trust your preparation** - You've got this!

---

## 📊 Domain Coverage Summary

| Domain                  | Weight | Pages to Study | Quick References | Priority    |
| ----------------------- | ------ | -------------- | ---------------- | ----------- |
| 1. Responsible AI       | 7%     | 1 module       | None             | Medium      |
| 2. Plans & Features     | 31%    | 4 modules      | 3 guides         | ⚡ HIGHEST  |
| 3. Data Handling        | 15%    | 2 modules      | 1 guide          | High        |
| 4. Prompt Engineering   | 9%     | 1 module       | 1 guide          | Medium-High |
| 5. Use Cases            | 14%    | 3 modules      | 2 guides         | High        |
| 6. Testing              | 9%     | 1 module       | 1 guide          | Medium-High |
| 7. Privacy & Exclusions | 15%    | 2 modules      | 2 guides         | High        |

**Total Coverage**: 9 Part 1 modules + 6 Part 2 modules + 12 Quick References

---

## 📞 Additional Resources

- **Official Study Guide**: [Microsoft Learn GH-300](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/gh-300)
- **GitHub Copilot Documentation**: [docs.github.com/copilot](https://docs.github.com/copilot)
- **GitHub Community**: [github.com/community](https://github.com/community)
- **Practice Assessment**: Available on Microsoft Learn

---

**Good luck on your GitHub Copilot certification exam! 🚀**

_Last Updated: Based on GH-300 exam objectives_
