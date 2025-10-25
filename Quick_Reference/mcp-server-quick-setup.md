# MCP Server Quick Setup Guide

## What is MCP?

**Model Context Protocol** = USB-C for AI tools (connects AI to data sources and tools)

## Three Setup Methods

| Method             | Complexity     | Best For                | Requirements          |
| ------------------ | -------------- | ----------------------- | --------------------- |
| **OAuth**          | ⚡ Easy        | Most users              | GitHub account        |
| **PAT**            | ⚡⚡ Moderate  | Advanced control        | Personal Access Token |
| **Docker (Local)** | ⚡⚡⚡ Complex | Enterprise restrictions | Docker + PAT          |

## Method 1: OAuth (Recommended)

**Steps**:

```
1. Ctrl+Shift+P (or Cmd+Shift+P)
2. Type: MCP: add server
3. Select: HTTP (HTTP or Server-Sent Events)
4. URL: https://api.githubcopilot.com/mcp/
5. Press Enter for default ID
6. Choose: User settings or Workspace
7. Click Allow → Sign in to GitHub
```

**Time**: ~30 seconds
**Result**: Ready to use immediately

## Method 2: Personal Access Token (PAT)

**When to use**: Need specific authentication control

**Steps**:

```
1. Create PAT with repo + read:packages scope
2. Follow OAuth steps but cancel authorization
3. Add to config:
   "headers": {
     "Authorization": "Bearer ${input:github_token}"
   }
4. Add input prompt:
   "inputs": [{
     "id": "github_token",
     "type": "promptString",
     "description": "GitHub Personal Access Token",
     "password": true
   }]
5. Restart MCP server
6. Enter PAT when prompted
```

## Method 3: Docker (Local) - Enterprise Only

**When to use**:

- GitHub Enterprise Server with PAT restrictions
- Need local control
- Enterprise policy requires it

**Requirements**:

- ✅ Docker installed and running
- ✅ PAT with necessary scopes
- ❌ OAuth NOT supported in this setup

**Config**:

```json
{
  "inputs": [
    {
      "type": "promptString",
      "id": "github_token",
      "description": "GitHub Personal Access Token",
      "password": true
    }
  ],
  "servers": {
    "github": {
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "-e",
        "GITHUB_PERSONAL_ACCESS_TOKEN",
        "ghcr.io/github/github-mcp-server"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${input:github_token}"
      }
    }
  }
}
```

## Quick Troubleshooting

| Issue                | Check          | Fix                                      |
| -------------------- | -------------- | ---------------------------------------- |
| **Connection fails** | GitHub sign-in | Confirm signed in to GitHub in VS Code   |
| **PAT auth fails**   | PAT scopes     | Ensure `repo` and `read:packages` scopes |
| **Config errors**    | Typos          | Double-check config file                 |
| **Docker fails**     | Docker status  | Ensure Docker is running                 |
| **Temp issues**      | Restart        | Restart VS Code or MCP Server            |

## Using MCP with Copilot Chat

**Steps**:

```
1. Open Copilot Chat in VS Code
2. Switch to Agent mode
3. Click "Select tools"
4. Use natural language prompts
```

**What you can do**:

- Create issues
- Summarize repositories
- Edit files
- Create branches
- Rank PRs/issues

## Configuration Locations

| Location               | Scope           | When to Use         |
| ---------------------- | --------------- | ------------------- |
| **User settings**      | All projects    | Global availability |
| **Workspace settings** | Current project | Project-specific    |

## 30+ Tools Available

| Category       | Examples              |
| -------------- | --------------------- |
| **Issues**     | Add, rank, prioritize |
| **Files**      | Edit, create, analyze |
| **PRs**        | Rank, manage, review  |
| **Repository** | Triage, track tasks   |

## Quick Decision: Which Method?

```
Can you use OAuth?
├─ Yes → OAuth (easiest, recommended)
└─ No → PAT or Docker

Need enterprise authentication?
├─ Yes → Check with admin about restrictions
│        ├─ Can use hosted → PAT
│        └─ Must be local → Docker
└─ No → OAuth

GitHub Enterprise Server?
├─ Yes → Docker (local)
└─ No → OAuth or PAT
```

## Key Benefits

✅ No Docker or config files (OAuth)
✅ Cross-platform (web, mobile, desktop)
✅ Enterprise auth support (Entra, Auth0)
✅ Auto-scaling
✅ 30+ tools ready to use

## Module Reference

📚 [Full Guide: Introduction to MCP Server](../Fundamentals_Part_2/3_Introduction_to_MCP_Server.md)
