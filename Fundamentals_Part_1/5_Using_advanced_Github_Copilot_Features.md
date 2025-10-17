# Advanced GitHub Copilot Features

**Ghost Text**: Auto-suggestions that appear as you type (accept with Tab)

**Chat Interface**: Click chat icon in left sidebar for interactive discussions

**Inline Chat**: `Ctrl+I` (Windows) or `Cmd+I` (Mac) - chat without leaving code

## Agents (Context-Specific Help)

| Agent | Context | Example Usage |
|-------|---------|---------------|
| `@workspace` | Entire project | `@workspace how can I package this project?` |
| `@terminal` | Terminal output | `@terminal How do I fix this error?` |
| `@file` | Specific file | `@file Can you refactor this function in main.py?` |
| `@directory` | Specific directory | `@directory How can I optimize the utils directory?` |

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/advanced-github-copilot/2-advanced-github-copilot-features)

# Applied GitHub Copilot Techniques

## Slash Commands (Implicit Prompts)

| Command | Purpose | Use Case |
|---------|---------|----------|
| `/fix` | Fix bugs in code | Select buggy code, use `/fix` in inline chat |
| `/doc` | Add documentation | Generate comments for functions/classes |
| `/explain` | Explain code | Understand complex code blocks |
| `/optimize` | Improve performance | Analyze and enhance runtime |
| `/tests` | Generate tests | Create unit tests for selected code |

**Example**: Select code with bug → `Ctrl+I` / `Cmd+I` → Type `/fix`

**Selective Context**: Combine agents with prompts for precise help
- `@workspace help me create a Dockerfile using Python Virtual Environment`
- `@terminal How do I fix the error I'm seeing?`
- `@file Can you refactor the main function in app.py?`

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/advanced-github-copilot/4-applied-copilot-techniques)
