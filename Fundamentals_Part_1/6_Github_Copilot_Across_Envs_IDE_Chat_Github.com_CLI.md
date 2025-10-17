# Code Completion with GitHub Copilot

**Supported Languages**: Python, JavaScript, Java, TypeScript, Ruby, Go, C#, C++ (plus many more)

**Auto Suggestions**: Real-time code completions as you type - saves time on syntax and common patterns

**Multiple Suggestions Pane**: Hover over suggestion → control panel appears → cycle with `Alt+]` / `Option+]` (next) or `Alt+[` / `Option+[` (previous)

## Copilot Adapts To Your Style

| Feature | How It Adapts |
|---------|---------------|
| Method Implementation | Suggests entire methods following your coding style |
| Naming Conventions | Picks up your variable/function naming preferences |
| Formatting | Matches indentation, bracket placement |
| Comment Style | Mimics inline/block/docstring preferences |
| Design Patterns | Aligns with patterns used in your project |

## Comment-Driven Code Generation

Copilot uses comments to generate better code:

| Comment Type | Purpose |
|--------------|---------|
| Inline comments | Short explanations for specific lines |
| Block comments | Longer function/class descriptions |
| Docstrings | Formal documentation (Python, etc.) |
| TODO comments | Future implementations |
| API Documentation | Function usage/parameters |

**Example**: Write `# Function to reverse a string` → Copilot generates implementation

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-across-environments/2-code-completion-with-git-hub-copilot)

# GitHub Copilot Chat

Access via chat icon in left navbar. Best for complex code generation, debugging, and explanations.

## Use Cases

| Scenario | Example |
|----------|---------|
| **Complex Code Generation** | Algorithms, data structures, regex patterns |
| **Debugging** | Analyze errors, suggest fixes (use inline chat on selected code) |
| **Code Explanations** | Break down complex snippets, explain async/await |

## Improving Chat Responses

**Scope Referencing**:
- `#file:filename.js` - Reference specific file
- `@workspace` - Reference entire solution/project

**Slash Commands**:
- `/doc` - Add comments to code
- `/explain` - Explain selected code
- `/fix` - Propose bug fixes
- `/generate` - Generate new code
- `/optimize` - Improve performance
- `/tests` - Create unit tests

## AI Models

| Model Type | PRU Cost | Best For |
|------------|----------|----------|
| **Standard (GPT-4o)** | 1 PRU | Routine coding, explanations, basic debugging |
| **Premium (o1-preview, o1-mini)** | 2 PRUs | Complex algorithms, security analysis, deep reasoning |

## Chat Agents

| Agent | Purpose | Example |
|-------|---------|---------|
| `@workspace` | Whole project context | `@workspace where is the calculate function?` |
| `@workspace /new` | Generate new project | `@workspace /new generate HTML pages for calculator` |
| `@terminal` | Command-line help | `@terminal find largest file in directory` |
| `@vscode` | IDE-specific questions | `@vscode how to debug?` |

**Feedback**: Use thumbs up/down buttons on suggestions

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-across-environments/3-git-hub-copilot-chat)

# GitHub Copilot on GitHub.com

AI assistance directly on GitHub web interface for repos, issues, PRs, discussions.

## Key Features

| Feature | Purpose | PRU Cost |
|---------|---------|----------|
| **Repository Exploration** | Code explanations, project overview, documentation | Standard |
| **PR Summaries** | Auto-generate PR descriptions and review suggestions | 1-2 PRUs |
| **Issue Management** | Analyze issues, suggest solutions, create reproduction steps | Standard |
| **Code Review** | Generate review comments, security/performance analysis | 1-3 PRUs |
| **GitHub Actions Errors** | Explain and resolve workflow failures | Standard |

**Example Uses**:
- "Explain the main functionality of this repository"
- "Summarize changes in this PR and highlight concerns"
- "Review this code for security and performance"

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-across-environments/4-git-hub-copilot-github-web)

# GitHub Copilot CLI

AI assistance for command-line workflows via GitHub CLI.

## Common Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `gh copilot explain` | Explain a command | `gh copilot explain "sudo apt-get"` |
| `gh copilot suggest` | Suggest command for task | `gh copilot suggest "Undo last commit"` |
| Execute command | Run suggested command | Choose "Execute command" after suggestion |
| Revise command | Rework suggestion | Choose "Revise command" with feedback |

## Configuration

**Set up `ghcs` alias for direct execution**:

```bash
# Bash
echo 'eval "$(gh copilot alias -- bash)"' >> ~/.bashrc

# PowerShell
$GH_COPILOT_PROFILE = Join-Path -Path $(Split-Path -Path $PROFILE -Parent) -ChildPath "gh-copilot.ps1"
gh copilot alias -- pwsh | Out-File ( New-Item -Path $GH_COPILOT_PROFILE -Force )
echo ". `"$GH_COPILOT_PROFILE`"" >> $PROFILE

# Mac/Zsh
echo 'eval "$(gh copilot alias -- zsh)"' >> ~/.zshrc
```

**Usage Data**: `gh copilot config` → "Optional Usage Analytics" → "No" to opt out

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-across-environments/5-git-hub-copilot-for-the-command-line)
