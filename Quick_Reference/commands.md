# GitHub Copilot Commands & Shortcuts

| Feature               | Shortcut (Windows/Linux) | Shortcut (Mac)       | Description                     |
| --------------------- | ------------------------ | -------------------- | ------------------------------- |
| **Command Palette**   | `Ctrl+Shift+P`           | `Cmd+Shift+P`        | Access all Copilot commands     |
| **Inline Chat**       | `Ctrl+I`                 | `Cmd+I`              | Context-specific chat in editor |
| **Accept Suggestion** | `Tab` or `→`             | `Tab` or `→`         | Accept inline suggestion        |
| **Reject Suggestion** | `Esc` or keep typing     | `Esc` or keep typing | Dismiss inline suggestion       |
| **Cycle Suggestions** | `Alt+]`                  | `Option+]`           | View alternative suggestions    |

## Slash Commands (in Inline Chat & Chat View)

| Command           | Purpose                   | Use Case                                     |
| ----------------- | ------------------------- | -------------------------------------------- |
| `/fix`            | Fix bugs in code          | Select buggy code, use `/fix` in inline chat |
| `/doc`            | Add documentation         | Generate comments for functions/classes      |
| `/explain`        | Explain code              | Understand complex code blocks               |
| `/optimize`       | Improve performance       | Analyze and enhance runtime                  |
| `/tests`          | Generate tests            | Create unit tests for selected code          |
| `/setupTests`     | Setup test framework      | Configure testing framework for project      |
| `/fixTestFailure` | Fix failing tests         | Get suggestions to fix test failures         |
| `/suggest`        | Offers code suggestions   | Get alternative implementations              |
| `/comment`        | Converts comments to code | Turn natural language into code              |

## Agents (Context-Specific Help)

| Agent        | Context            | Example Usage                                        |
| ------------ | ------------------ | ---------------------------------------------------- |
| `@workspace` | Entire project     | `@workspace how can I package this project?`         |
| `@terminal`  | Terminal output    | `@terminal How do I fix this error?`                 |
| `@file`      | Specific file      | `@file Can you refactor this function in main.py?`   |
| `@directory` | Specific directory | `@directory How can I optimize the utils directory?` |

## Quick Reference

| Action                 | How To                                                |
| ---------------------- | ----------------------------------------------------- |
| **Copilot Chat**       | Open chat panel, ask questions in natural language    |
| **Inline Suggestions** | Start typing, Copilot shows grayed-out completions    |
| **Comments to Code**   | Write comment describing functionality, press Enter   |
| **Explain Code**       | Right-click code → "Copilot: Explain This"            |
| **Generate Tests**     | Command Palette → "Copilot: Generate Unit Tests"      |
| **Ghost Text**         | Auto-suggestions appear as you type (accept with Tab) |

## Advanced Usage Examples

**Fix Bug**: Select code with bug → `Ctrl+I` / `Cmd+I` → Type `/fix`

**Selective Context**: Combine agents with prompts

- `@workspace help me create a Dockerfile using Python Virtual Environment`
- `@terminal How do I fix the error I'm seeing?`
- `@file Can you refactor the main function in app.py?`
