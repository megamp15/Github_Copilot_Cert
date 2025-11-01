# GitHub Copilot Certification Exam Experience

## Question Format

- **Many questions** were in the format: **"Select 2 out of 4 options"**
  - Pay close attention to questions that ask for multiple correct answers
  - Review all options carefully before selecting

## Important Topics to Focus On

These areas appeared frequently on the exam and are worth extra attention during preparation:

### 1. GitHub CLI Commands

The exam had **very specific questions** about GitHub CLI commands for Copilot. Key areas to know:

- **`gh copilot explain`** - Explain a command
- **`gh copilot suggest`** - Suggest command for a task
- **`gh copilot alias`** - Set up shell aliases (`ghcs`)
- **`gh copilot config`** - Configure usage analytics and settings
- **`gh issue edit --add-assignee copilot`** - Assign issues to Copilot via CLI

📚 **Reference**: [GitHub Copilot Across Environments - CLI Section](Fundamentals_Part_1/6_Github_Copilot_Across_Envs_IDE_Chat_Github.com_CLI.md#github-copilot-cli)

### 2. APIs for GitHub Copilot Organizational Management

Questions about **REST APIs** for interacting with GitHub Copilot at organizational level:

- **Usage Metrics API**:
  - `GET /enterprises/{enterprise}/copilot/usage`
  - `GET /orgs/{org}/copilot/usage`
  - `GET /enterprises/{enterprise}/team/{team_slug}/copilot/usage`
- **GraphQL API** for assigning issues to Copilot programmatically

📚 **Reference**: [Developer Use Cases - REST API Section](Fundamentals_Part_1/8_Developer_use_cases_for_AI_with_Github_Copilot.md#rest-api-for-copilot-usage-metrics)

📚 **Reference**: [Coding Agent - GraphQL API Section](Fundamentals_Part_2/2_Accelerate_development_with_Github_Copilot_coding_agent.md#method-4-graphql-api)

### 3. Knowledge Bases - Plan Availability

**Important**: Knowledge Bases are **Enterprise plan ONLY**

- Available features:
  - Attach knowledge bases to tailor chat responses
  - Custom model training on internal codebase
  - Codebase indexing

📚 **Reference**: [Management & Customization - Plan Features](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md#plan-features-comparison)

📚 **Reference**: [Subscription Plans Quick Guide](Quick_Reference/subscription-plans.md)

### 4. Public Code Detection / Duplicate Detection Filter

Questions about **matching public code** settings and how to enable/disable the filter:

- **Setting Location**: Organization/Enterprise Settings → Copilot → Under Suggestions → **Matching public code**
- **Options**: **Block** or **Allow**
- **Purpose**: Filters out suggestions that match public code to minimize overlap and reduce risk
- **IP Indemnity Requirement**: Must be set to **Block** for IP indemnity protection (Business & Enterprise plans)
- **Availability**: Available on **all plans** (Free, Pro, Business, Enterprise)

**Steps to Enable/Configure**:

1. Profile photo → Your enterprises/organizations
2. Next to enterprise/org → **Settings**
3. Left sidebar → **Copilot**
4. Under Suggestions → Matching public code → **Block** or **Allow**
5. **Save**

📚 **Reference**: [Management & Customization - Matching Public Code](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md#explore-contractual-protections-in-github-copilot-and-disabling-matching-public-code)

📚 **Reference**: [Subscription Plans - Public Code Filtering](Quick_Reference/subscription-plans.md#public-code-filtering-all-plans)

### 5. Content Exclusion

Questions about **content exclusions** - what they do, how to configure them, and their limitations:

**What Content Exclusions Do**:

- ❌ No code completion in affected files
- ❌ Content won't inform suggestions in other files
- ❌ Content won't inform Copilot Chat responses

**Configuration Levels**:

**Repository Level**:

1. Repo main page → **Settings**
2. Code & automation → **Copilot** → **Content exclusion**
3. In "Paths to exclude in this repository" box, specify paths to exclude
   - Format: `"/PATH/TO/DIRECTORY/OR/FILE"` (one per line)
   - Supports wildcard patterns (e.g., `"**/.env"`, `"**/.env.*"`)

**Important**:

- ❌ **`.gitignore` does NOT affect Copilot** - `.gitignore` only affects Git tracking, not Copilot behavior
- ✅ File-level exclusion is done by **specifying paths** in repository/organization settings (not via a file in the repo)

**Organization Level**:

1. Profile → **Your organizations** → **Settings**
2. **Copilot** → **Content exclusion**
3. Enter files/repos to exclude

**Availability**: **Business and Enterprise plans only**

**Important Limitations**:

- May not apply in Copilot Chat with `@github` participant
- Copilot may use type info from excluded files if referenced in non-excluded files
- Only applies to org members
- Changes take up to 30 minutes to apply (reload IDE for immediate effect)

📚 **Reference**: [Management & Customization - Content Exclusions](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md#manage-content-exclusions)

### 6. GitHub Copilot in IDEs vs GitHub.com

The exam had specific questions about **what features are available where**:

#### In IDEs (VS Code, JetBrains, etc.):

- Inline code suggestions
- Inline chat (`Ctrl+I` / `Cmd+I`)
- Chat panel for complex discussions
- Code explanations (right-click → "Copilot: Explain This")
- Test generation in IDE
- Agent Mode for autonomous local edits
- Slash commands (`/fix`, `/explain`, `/tests`, `/doc`, etc.)
- `@workspace` for project-wide context

#### On GitHub.com:

- PR summaries (auto-generate descriptions)
- Code review suggestions
- Issue analysis and solutions
- Repository exploration
- GitHub Actions error explanations
- Assign Copilot to issues (Coding Agent)
- Create PR requests for Copilot

📚 **Reference**: [GitHub Copilot Across Environments](Fundamentals_Part_1/6_Github_Copilot_Across_Envs_IDE_Chat_Github.com_CLI.md)

📚 **Reference**: [Copilot Across Platforms Quick Guide](Quick_Reference/copilot-across-platforms.md)

### 7. What GitHub CLI Allows/Enables

Specific questions about GitHub CLI capabilities with Copilot:

- Can assign Copilot to issues via CLI
- Can explain commands and suggest commands via `gh copilot`
- Supports alias setup (`ghcs`) for direct execution
- Can configure usage analytics preferences
- Works across platforms (Bash, PowerShell, Zsh)

📚 **Reference**: [GitHub CLI Commands](Quick_Reference/commands.md)

### 8. Subscription Plan Features

Questions about which features are available on which plans:

- **Free**: 2000 completions/month, 50 chats/month
- **Pro/Pro+**: Unlimited completions, all IDE features
- **Business**: Team management, IP indemnity, security filtering, content exclusions, usage metrics
- **Enterprise**: All Business features + Knowledge Bases, custom models, codebase indexing

📚 **Reference**: [Subscription Plans Comparison](Quick_Reference/subscription-plans.md)

## Key Takeaways for Future Test-Takers

1. **Memorize GitHub CLI commands** - `gh copilot explain`, `gh copilot suggest`, `gh copilot config`, `gh copilot alias`
2. **Know the API endpoints** for usage metrics at enterprise/org/team levels
3. **Remember plan-specific features** - Especially Knowledge Bases (Enterprise only), Content Exclusions (Business/Enterprise only)
4. **Understand feature availability** - What works in IDE vs GitHub.com vs CLI
5. **Know how to configure** - Public code detection settings, Content exclusions (repository and org levels)
6. **Pay attention to "select 2" questions** - Read carefully for multiple correct answers

## Where to Find More Information

### GitHub CLI

- [Fundamentals Part 1 - Module 6: GitHub Copilot Across Environments](Fundamentals_Part_1/6_Github_Copilot_Across_Envs_IDE_Chat_Github.com_CLI.md)

### APIs

- [Fundamentals Part 1 - Module 8: Developer Use Cases](Fundamentals_Part_1/8_Developer_use_cases_for_AI_with_Github_Copilot.md)
- [Fundamentals Part 2 - Module 2: Coding Agent](Fundamentals_Part_2/2_Accelerate_development_with_Github_Copilot_coding_agent.md)

### Plans and Features

- [Fundamentals Part 1 - Module 7: Management & Customization](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md)
- [Subscription Plans Quick Reference](Quick_Reference/subscription-plans.md)

### Public Code Detection & Content Exclusions

- [Fundamentals Part 1 - Module 7: Management & Customization](Fundamentals_Part_1/7_Management_and_Customization_considerations_with_Github_Copilot.md)

### IDE vs GitHub.com

- [Fundamentals Part 1 - Module 6: GitHub Copilot Across Environments](Fundamentals_Part_1/6_Github_Copilot_Across_Envs_IDE_Chat_Github.com_CLI.md)
- [Copilot Across Platforms Quick Guide](Quick_Reference/copilot-across-platforms.md)
