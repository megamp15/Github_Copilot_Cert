# When to Use What - GitHub Copilot Quick Decision Guide

## 🎯 Choose Your Tool Based on Task

| Task                      | Best Tool                           | Why                                            |
| ------------------------- | ----------------------------------- | ---------------------------------------------- |
| Quick code completion     | **Inline Suggestions**              | Fastest, appears as you type                   |
| Complex algorithm         | **Copilot Chat**                    | Better for multi-step reasoning                |
| Fix a bug                 | **Inline Chat** (`Ctrl+I`) + `/fix` | Context-specific, right where you code         |
| Understand code           | **Right-click** → Explain           | Quick explanation without context switch       |
| Generate tests            | **Smart action** or `/tests`        | Smart action fastest, /tests for comprehensive |
| Setup test framework      | **Chat** → `/setupTests`            | Configures framework automatically             |
| Fix failing test          | **Test Explorer sparkle icon**      | One-click fix suggestions                      |
| CLI help                  | **gh copilot suggest**              | Terminal-specific suggestions                  |
| PR review                 | **GitHub.com Copilot**              | Web-based PR analysis                          |
| Project-wide question     | **@workspace**                      | Understands entire codebase                    |
| Runbook/playbook/workflow | **Copilot Space**                   | Curated context, repeatable answers            |

## 💡 Workflow Recommendations

### Writing New Code

1. Write comment describing what you want
2. Let inline suggestions appear
3. If complex → `Ctrl+I` → describe in detail
4. If very complex → Open Chat → use role prompting

### Debugging

1. Select buggy code
2. `Ctrl+I` → `/fix`
3. If unclear → Chat → `/explain` the error
4. For CLI errors → `@terminal` agent

### Learning Unfamiliar Code

1. Right-click → "Copilot: Explain This"
2. For deeper understanding → Chat → `/explain #file:filename.js`
3. For whole project → `@workspace explain architecture`

### Documentation

1. Select function → `/doc` in inline chat
2. For README → Chat → `@workspace generate README`
3. For API docs → `/doc` with specific instructions

### Testing

1. First time → Chat → `/setupTests` (configures framework)
2. Quick test generation → Select code → Right-click → "Generate Tests"
3. Comprehensive tests → Select code → `Ctrl+I` → `/tests` with requirements
4. Fix failing test → Test Explorer → Hover → Click sparkle icon
5. Or Chat → `/fixTestFailure`

## ⚡ PRU (Premium Request Units) Management

| Action                 | PRU Cost | When to Use                           |
| ---------------------- | -------- | ------------------------------------- |
| Inline suggestions     | 0 PRUs   | Always!                               |
| Standard chat (GPT-4o) | 1 PRU    | Most tasks                            |
| Premium models (o1)    | 2 PRUs   | Complex algorithms, security analysis |
| PR summaries           | 1-2 PRUs | When needed for reviews               |
| Code review            | 1-3 PRUs | Important changes                     |
| @workspace queries     | 1-5 PRUs | When project context needed           |

**Tip**: Use inline suggestions and standard chat for routine work. Save premium models and workspace queries for complex tasks.

## 🚀 Speed vs Quality Trade-offs

| Speed          | Quality | Use Case                         | Tool                         |
| -------------- | ------- | -------------------------------- | ---------------------------- |
| ⚡⚡⚡ Fastest | Good    | Autocomplete, boilerplate        | Inline suggestions           |
| ⚡⚡ Fast      | Better  | Targeted help, quick fixes       | Inline chat + slash commands |
| ⚡ Slower      | Best    | Complex problems, learning       | Chat with premium models     |
| 🐌 Slowest     | Best    | Project generation, architecture | @workspace /new              |
