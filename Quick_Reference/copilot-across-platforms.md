# GitHub Copilot Across Platforms - Quick Reference

## 🖥️ IDE (VS Code, JetBrains, etc.)

### Best For
- Writing code
- Real-time suggestions
- Debugging
- Testing

### Key Features
| Feature | Shortcut | When to Use |
|---------|----------|-------------|
| Inline suggestions | Auto (Tab to accept) | Constant use while coding |
| Inline chat | `Ctrl+I` / `Cmd+I` | Quick questions in context |
| Chat panel | Click chat icon | Complex discussions |
| Explain code | Right-click | Understanding existing code |

### Pro Tips
- Keep related files open for better context
- Use `/fix` on selected code for debugging
- Use `@workspace` for project-wide questions

---

## 💬 Copilot Chat (In IDE)

### Best For
- Complex algorithms
- Learning new concepts
- Project architecture
- Deep debugging

### Slash Commands Quick Reference
```
/fix      - Fix bugs
/explain  - Explain code
/tests    - Generate tests
/doc      - Add documentation
/optimize - Improve performance
/generate - Create new code
```

### Agents
```
@workspace  - Project context
@terminal   - CLI help
@vscode     - IDE help
@file       - Specific file
@directory  - Specific folder
```

---

## 🌐 GitHub.com

### Best For
- PR reviews
- Issue triage
- Repository exploration
- Collaboration

### Key Features
| Feature | PRU Cost | Use Case |
|---------|----------|----------|
| PR summaries | 1-2 | Understand changes quickly |
| Code review | 1-3 | Security/performance analysis |
| Issue analysis | Standard | Break down problems |
| Repo exploration | Standard | Understand new codebases |
| Actions errors | Standard | Debug CI/CD failures |

### When to Use
- Reviewing PRs (auto-generate summaries)
- Analyzing complex issues
- Onboarding to new repos
- Troubleshooting Actions

---

## ⌨️ Command Line (CLI)

### Best For
- Terminal commands
- Git operations
- System administration
- Learning CLI tools

### Essential Commands
```bash
# Explain any command
gh copilot explain "docker-compose up -d"

# Get command suggestions
gh copilot suggest "find all Python files modified today"

# Interactive help
ghcs suggest "compress all .log files"
```

### Setup Once
```bash
# Set up ghcs alias for direct execution
gh copilot alias -- bash >> ~/.bashrc  # Linux/Mac
gh copilot alias -- zsh >> ~/.zshrc    # Mac (Zsh)
# See full guide for PowerShell
```

---

## 🔄 Cross-Platform Workflow

### Example: Full Feature Development

1. **Planning (GitHub.com)**
   - Analyze issue with Copilot
   - Get implementation suggestions

2. **Coding (IDE)**
   - Use inline suggestions for speed
   - Use chat for complex logic
   - Use `@workspace` for project context

3. **Testing (IDE)**
   - Generate tests with `/tests`
   - Debug with `/fix` on failures

4. **CLI Operations**
   - `gh copilot suggest "git commands for feature branch"`

5. **Review (GitHub.com)**
   - Auto-generate PR summary
   - Get code review suggestions

---

## 📊 Platform Comparison

| Platform | Speed | Context | Best Use | PRU Usage |
|----------|-------|---------|----------|-----------|
| **IDE Inline** | ⚡⚡⚡ | Local file | Quick completions | Low (0-1) |
| **IDE Chat** | ⚡⚡ | Full project | Complex tasks | Medium (1-2) |
| **GitHub.com** | ⚡ | Repository | Collaboration | Medium (1-3) |
| **CLI** | ⚡⚡ | Terminal | Commands | Low (1) |

---

## 💰 PRU Optimization Tips

### Low PRU Activities (Do Often)
- Inline code suggestions (IDE)
- Simple CLI explanations
- Standard chat with GPT-4o
- Code explanations

### High PRU Activities (Use Wisely)
- Premium models (o1)
- @workspace queries
- Full PR reviews
- Project generation (@workspace /new)

### Best Practice
Mix platforms based on task:
- **80% of time**: IDE inline suggestions (free/low cost)
- **15% of time**: Standard chat and CLI (1 PRU each)
- **5% of time**: Premium features when truly needed (2-5 PRUs)
