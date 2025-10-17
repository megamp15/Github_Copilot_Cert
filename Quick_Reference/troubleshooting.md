# GitHub Copilot Troubleshooting Quick Guide

## 🚫 No Code Suggestions Appearing

| Check | Fix |
|-------|-----|
| **Internet** | Verify active connection (Copilot requires internet) |
| **Extension version** | Update GitHub Copilot extension to latest |
| **IDE compatibility** | Confirm IDE supports Copilot, check configs |
| **Content exclusions** | Check if file is excluded (see icon on status bar) |
| **Copilot enabled** | Click Copilot icon in status bar → Enable |

### Quick Test
1. Check status bar icon - should be visible without diagonal line
2. Type a comment like `// function to add two numbers`
3. Press Enter and wait 2-3 seconds
4. If no suggestion → troubleshoot above

---

## ⚙️ Content Exclusions Not Working

| Issue | Solution |
|-------|----------|
| **Just configured** | Wait 30 mins OR reload IDE to apply immediately |
| **Not sure if active** | Hover over Copilot icon - diagonal line = exclusion active |
| **Chat still working** | Expected - some features (Chat with `@github`) bypass exclusions |
| **Wrong scope** | Exclusions only apply to org members where configured |

### Verify Exclusion Status
```
Status bar icon with diagonal line (⊘) = File is excluded
Normal icon = File is included
```

---

## 😞 Suggestions Are Poor Quality

| Improve By | How |
|-----------|-----|
| **Add context** | Write descriptive comments above code |
| **Better naming** | Use meaningful variable/function names |
| **Trigger manually** | `Ctrl+Enter` (VS Code) to force suggestion |
| **Longer prompts** | Add more detail to comments |
| **Provide examples** | Include example usage in comments |
| **Iterate** | Erase suggestion, add detail, try again |

### Example - Bad vs Good Prompts

❌ **Bad**:
```javascript
// calc
```

✅ **Good**:
```javascript
// Function to calculate compound interest
// Parameters: principal (initial amount), rate (annual %), time (years)
// Returns: final amount after compound interest
```

---

## 🔄 Copilot Stopped Working Suddenly

1. **Check subscription** - Verify not expired (Free tier limits?)
2. **Restart IDE** - Simple but often effective
3. **Sign out/in** - Status bar icon → Sign out → Sign in
4. **Check GitHub status** - Visit https://www.githubstatus.com
5. **Reinstall extension** - Last resort

---

## 📝 Specific File Types Not Getting Suggestions

| Issue | Likely Cause | Fix |
|-------|--------------|-----|
| Config files (.env, etc.) | Intentionally excluded for security | Expected behavior |
| New file type | Language not well-supported | Try adding file extension context |
| Large files | Exceeds context window | Break into smaller files |

---

## 🔐 Content Exclusion Scenarios

### How Content Exclusions Work

**When you exclude a file/path**:
- ❌ No completions in that file
- ❌ Content won't inform suggestions elsewhere
- ❌ Content won't inform Chat responses

**Limitations**:
- May not apply in all Chat scenarios (`@github` participant)
- Type info might still leak through non-excluded files
- Only applies to your org members
- Takes up to 30 minutes to propagate

### Check If File Is Excluded
1. Look at Copilot icon in status bar
2. Diagonal line through icon = Excluded
3. Hover for details (org vs repo exclusion)

---

## 💬 Chat Issues

| Problem | Solution |
|---------|----------|
| Chat not responding | Check internet, restart IDE |
| Irrelevant answers | Use `#file:` or `@workspace` for context |
| Can't use slash commands | Type `/` and select from dropdown |
| Agent not working | Ensure `@workspace` etc. are available in your plan |

---

## 🛠️ Advanced Troubleshooting

### View Logs (VS Code)
1. `Ctrl+Shift+P` / `Cmd+Shift+P`
2. Type "Developer: Open Log File"
3. Or "Developer: Open Extensions Logs Folder"
4. Look for GitHub Copilot errors

### Collect Diagnostics
1. `Ctrl+Shift+P` / `Cmd+Shift+P`
2. "GitHub Copilot: Collect Diagnostics"
3. Share with support if needed

### Network Issues
- Check firewall/proxy settings
- Copilot needs outbound HTTPS access
- Corporate networks may block AI services

---

## ⏱️ Performance Issues

| Symptom | Fix |
|---------|-----|
| Slow suggestions | Close unused tabs, reduce open files |
| High CPU usage | Restart IDE, update extension |
| Laggy IDE | Disable other extensions temporarily |

---

## 📞 Still Stuck?

1. **GitHub Community** - https://github.com/community
2. **Documentation** - https://docs.github.com/copilot
3. **Support** - Via GitHub settings (paid plans)
4. **Status page** - https://www.githubstatus.com

---

## ✅ Quick Checklist

Before seeking help, verify:
- [ ] Internet connection active
- [ ] Extension updated to latest version
- [ ] Signed in to GitHub account
- [ ] Subscription active/not expired
- [ ] File not in exclusion list
- [ ] IDE restarted
- [ ] Logs checked for errors
