# Explore GitHub Copilot plans and their associated management and customization features

## Plan Features Comparison

### Management Policies

| Feature | Free & Pro | Business | Enterprise |
|---------|-----------|----------|------------|
| Public code filter | ✅ | ✅ | ✅ |
| User management | ❌ | ✅ | ✅ |
| Data excluded from training | ❌ | ✅ | ✅ |
| Enterprise-grade security | ❌ | ✅ | ✅ |
| IP indemnity | ❌ | ✅ | ✅ |
| Content exclusions | ❌ | ✅ | ✅ |
| SAML SSO | ❌ | ✅ | ✅ |
| Usage metrics | ❌ | ✅ | ✅ |

### Customization Features

| Feature | Free & Pro | Business | Enterprise |
|---------|-----------|----------|------------|
| Tailor chat to private codebase | ❌ | ❌ | ✅ |
| Unlimited Copilot Extensions | ✅ | ✅ | ✅ |
| Build private extensions | ✅ | ✅ | ✅ |
| Attach knowledge bases | ❌ | ❌ | ✅ |

## Key Selection Factors

| Factor | Why It Matters | Plans |
|--------|----------------|-------|
| **Data privacy & security** | Exclude files, audit logs, IP indemnity | Business, Enterprise |
| **Policy management** | Org-level controls for sensitive data | Business, Enterprise |
| **IP indemnity** | Legal protection against IP claims | Business, Enterprise |
| **Usage metrics** | Track team adoption and usage | Business, Enterprise |

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-management-and-customizations/2-explore-github-copilot-plans-associated-management-customization-features)

# Explore contractual protections in GitHub Copilot and disabling matching public code

## IP Indemnity (Business & Enterprise Only)

GitHub assumes legal responsibility if Copilot suggestions infringe third-party IP rights.

**Requirement**: "Matching public code" setting must be **blocked**

## Data Protection Agreement (DPA)

Outlines data protection measures and compliance with privacy regulations.

## GitHub Copilot Trust Center

Resource for security, privacy, compliance, and IP safeguards information.

## Filtering Matching Public Code

**Steps to Block**:
1. Profile photo → Your enterprises/organizations
2. Next to enterprise/org → **Settings**
3. Left sidebar → **Copilot**
4. Under Suggestions → Matching public code → **Block**
5. **Save**

**Why**: Minimizes code overlap with public code, reduces risk of incorporating insecure/noncompliant code

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-management-and-customizations/3-github-copilot-contractual-protections-disabling-matching-public-code)

# Manage content exclusions

## What Gets Excluded

When you exclude content:
- ❌ No code completion in affected files
- ❌ Content won't inform suggestions in other files
- ❌ Content won't inform Copilot Chat responses

## Configuration

### Repository Level
1. Repo main page → **Settings**
2. Code & automation → **Copilot**
3. Specify paths to exclude

### Organization Level
1. Profile → **Your organizations** → **Settings**
2. **Copilot** → **Content exclusion**
3. Enter files/repos to exclude

## Limitations

| Limitation | Impact |
|------------|--------|
| **IDE limitations** | May not apply in Copilot Chat with `@github` participant |
| **Semantic info** | Copilot may use type info from excluded files if referenced in non-excluded files |
| **Policy scope** | Only applies to org members; others can still see suggestions |
| **Application delay** | Changes take up to 30 minutes (reload IDE for immediate effect) |

## Impact Considerations

**Benefits**: More secure/compliant suggestions

**Trade-offs**: Reduced context → potentially less accurate suggestions

**Example**: Excluding config file → Copilot can't suggest code depending on those configs

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-management-and-customizations/4-manage-content-exclusions)

# Troubleshoot common problems with GitHub Copilot

## Missing Code Suggestions

| Issue | Solution |
|-------|----------|
| No internet | Check connection (Copilot requires active connection) |
| Outdated extension | Update GitHub Copilot extension |
| IDE incompatible | Verify IDE compatibility and configuration |
| Content excluded | Check content exclusion settings |

## Content Exclusions Not Working

| Problem | Fix |
|---------|-----|
| **Delayed application** | Wait 30 mins or reload IDE settings |
| **Inadequate scope** | Check icon on status bar (diagonal line = exclusion active) |
| **IDE limitations** | Aware some features (Chat) may bypass exclusions |

**Check Status**: Hover over Copilot icon on status bar - diagonal line indicates exclusion is active

## Unsatisfactory Suggestions

| Technique | How |
|-----------|-----|
| **Provide context** | Descriptive comments, meaningful variable names |
| **Use commands** | `Ctrl+Enter` (VS Code) to trigger suggestions |
| **Adjust prompt** | Longer/more detailed prompts often better |
| **Iterate** | Try rephrasing or adding examples |

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/github-copilot-management-and-customizations/5-troubleshoot-common-issues-with-github-copilot)
