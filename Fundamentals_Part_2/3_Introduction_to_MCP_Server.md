# Simplify your AI workflow with GitHub MCP Server

## Overview

**Challenge**: Making AI tools available across all environments (web, mobile, desktop) can be complex

**Solution**: GitHub MCP Server provides a simple, scalable way to integrate GitHub Copilot with your code, tools, and workflows

**Built on**: Model Context Protocol (MCP) - removes setup friction and unlocks powerful capabilities

## What is MCP?

**MCP (Model Context Protocol)** = USB-C standard for AI tools

**Purpose**: Provides a consistent and secure way for AI models to connect to tools and data sources

### MCP Key Benefits

| Benefit                  | What It Means                                                       |
| ------------------------ | ------------------------------------------------------------------- |
| **Growing library**      | Access tools your AI models can use immediately                     |
| **Flexibility**          | Work with different AI providers while keeping workflows consistent |
| **Seamless integration** | Integrates into existing development environment and processes      |

## How MCP Clients Connect to Servers

MCP Clients (like Claude, IDEs, or other tools) can interact with MCP Servers in **3 different ways**:

### 1. Local Communication with Local Data

**Architecture**: MCP Client → MCP Server (local) → Local Data Source

**How it works**:

- Client talks directly to MCP Server running on your machine (MCP Protocol)
- Server connects to local data sources (files, databases, local resources)

**When to use**:

- Local development
- Fast access to private data on your machine
- Data needs to stay local for security/privacy

**Example use cases**:

- Accessing local file system
- Querying local databases
- Working with local code repositories

### 2. Local Server as Bridge to Remote Services

**Architecture**: MCP Client → MCP Server (local) → Web APIs → Remote Service

**How it works**:

- Client connects to MCP Server running locally
- Server bridges to remote services via Web APIs
- Local server handles caching, security, preprocessing

**When to use**:

- Need to fetch/update info from remote services
- Benefit from local server as intermediary
- Want caching, security checks, or data preprocessing

**Example use cases**:

- Fetching data from cloud APIs with local caching
- Security checks before sending data externally
- Data preprocessing before remote operations

### 3. Remote Communication Over the Internet

**Architecture**: MCP Client → MCP Server (remote/internet) → Web APIs → External Services

**How it works**:

- Client connects to MCP Server hosted on the internet
- Remote server communicates with other external services via Web APIs
- No local server needed

**When to use**:

- Resources/computation can't happen locally
- Need cloud-based compute
- Using SaaS platforms or third-party integrations

**Example use cases**:

- Cloud-based computation
- SaaS platform integrations
- Third-party services that only exist online

## MCP Connection Patterns Summary

| Pattern              | Server Location | Data/Service Location | Best For                   | Example                  |
| -------------------- | --------------- | --------------------- | -------------------------- | ------------------------ |
| **Local-to-Local**   | Local           | Local                 | Private, fast local access | Local file operations    |
| **Local-to-Remote**  | Local           | Remote                | Caching, security layer    | API calls with caching   |
| **Remote-to-Remote** | Remote          | Remote                | Cloud services, SaaS       | Cloud-based integrations |

## Why Use GitHub MCP Server?

### The Problem with Traditional Local MCP Servers

| Traditional Setup Issue    | Impact                             |
| -------------------------- | ---------------------------------- |
| **Docker required**        | Complex setup                      |
| **Token management**       | Manual configuration needed        |
| **Manual configuration**   | Slows down setup                   |
| **Web client limitations** | Blocks integration with GitHub.com |

### GitHub MCP Server Solution

**GitHub-hosted server** = Quick, easy, no Docker or config files needed

### Key Benefits

| Benefit                        | What You Get                                                   |
| ------------------------------ | -------------------------------------------------------------- |
| **No Docker**                  | Eliminates need for Docker or manual configuration files       |
| **One-click OAuth**            | Easy authentication with single click                          |
| **Cross-platform**             | Work seamlessly across web, desktop, and mobile                |
| **Enterprise authentication**  | Supports Entra, Auth0, and other enterprise identity providers |
| **Auto-scaling**               | Scales automatically to meet usage needs                       |
| **Advanced features**          | Semantic code search, automated fixes                          |
| **GitHub Copilot integration** | Use AI tools like Copilot Chat across web and mobile           |

### Benefits Comparison

| Aspect               | Local MCP Server              | GitHub MCP Server       |
| -------------------- | ----------------------------- | ----------------------- |
| **Setup complexity** | High (Docker, config, tokens) | Low (one-click OAuth)   |
| **Web integration**  | Blocked                       | Seamless                |
| **Mobile support**   | Limited                       | Full support            |
| **Enterprise auth**  | Manual setup                  | Built-in (Entra, Auth0) |
| **Scaling**          | Manual                        | Automatic               |
| **Maintenance**      | Self-managed                  | GitHub-managed          |

## GitHub MCP Server in Action

**What it is**: Open-source server connecting GitHub Copilot and AI tools directly to your repositories

### Core Capabilities

| Capability            | What You Can Do                     |
| --------------------- | ----------------------------------- |
| **Code analysis**     | Analyze and summarize code          |
| **Issue management**  | Create and manage issues            |
| **PR management**     | Create and manage pull requests     |
| **Repository triage** | Automate triage and task tracking   |
| **Semantic search**   | Advanced code search capabilities   |
| **Automated fixes**   | Boost workflow with automated fixes |

### Available Tools

**30+ tools** currently available, including:

| Tool Category        | Examples                                     |
| -------------------- | -------------------------------------------- |
| **Issue operations** | Add issues, rank issues, identify priorities |
| **File operations**  | Edit files, create branches                  |
| **PR operations**    | Rank PRs, manage pull requests               |
| **Repository tasks** | Automate triage, track tasks                 |

### What You Can Do

**Development tasks**:

- ✅ Add issues easily
- ✅ Edit files quickly
- ✅ Create branches
- ✅ Rank pull requests by priority
- ✅ Rank issues to identify what's important
- ✅ Better understand projects through code analysis
- ✅ Save time with automated triage

## Use Case Examples

| Scenario                   | How GitHub MCP Server Helps                         |
| -------------------------- | --------------------------------------------------- |
| **Code review**            | Analyze and summarize code for better understanding |
| **Issue triage**           | Automatically rank and prioritize issues            |
| **PR management**          | Rank PRs to focus on high-priority changes          |
| **Repository maintenance** | Automate task tracking and triage                   |
| **Cross-platform work**    | Work seamlessly from web, desktop, or mobile        |

## Key Advantages

| Advantage            | Benefit                                         |
| -------------------- | ----------------------------------------------- |
| **Simplicity**       | No Docker, no config files, one-click setup     |
| **Cross-platform**   | Web, mobile, desktop all supported              |
| **Enterprise-ready** | Secure authentication with enterprise providers |
| **Scalable**         | Auto-scales to meet your needs                  |
| **Feature-rich**     | 30+ tools for comprehensive workflow support    |
| **Open-source**      | Transparent, community-driven                   |

## Quick Decision Guide

### Use GitHub MCP Server When:

✅ Want quick setup without Docker
✅ Need to work across web, mobile, and desktop
✅ Require enterprise authentication (Entra, Auth0)
✅ Want automated scaling
✅ Need semantic code search
✅ Want 30+ ready-to-use tools
✅ Need GitHub Copilot integration

### Consider Local MCP Server When:

⚠️ Need complete control over server environment
⚠️ Have specific custom server requirements
⚠️ Can't use GitHub-hosted services due to policy
⚠️ Need highly specialized local-only functionality

## MCP Protocol Analogy

**MCP is like USB-C for AI**:

| USB-C Feature             | MCP Equivalent                        |
| ------------------------- | ------------------------------------- |
| **Universal connector**   | Works with any AI provider            |
| **Standardized protocol** | Consistent communication method       |
| **Plug and play**         | Easy integration with existing tools  |
| **Future-proof**          | Growing ecosystem of compatible tools |

## Key Takeaways

✅ **MCP = Standard protocol**: Like USB-C for AI tools (consistent, secure connections)
✅ **3 connection patterns**: Local-to-local, local-to-remote, remote-to-remote
✅ **GitHub MCP Server simplifies setup**: No Docker, one-click OAuth, auto-scaling
✅ **Cross-platform support**: Web, desktop, mobile all work seamlessly
✅ **Enterprise-ready**: Supports Entra, Auth0, and other identity providers
✅ **30+ tools available**: Issues, PRs, files, branches, semantic search, automated fixes
✅ **Open-source**: Transparent and community-driven
✅ **Copilot integration**: Direct connection to GitHub Copilot and AI tools
✅ **Automated workflows**: Issue triage, PR ranking, task tracking
✅ **Better than local**: Eliminates Docker, config files, token management complexity

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/mcp-server/2-simplify-workflow)

# Configure, connect, and use GitHub MCP Server in VS Code

## Overview

Learn how to set up and use GitHub MCP Server in Visual Studio Code to bring AI-powered workflows directly into your development environment.

**You'll learn**:

- How to set up using OAuth or Personal Access Token (PAT)
- Optional local setup using Docker for more control
- How to use with Copilot Chat for AI-powered productivity
- Common troubleshooting steps

## Setup Methods Comparison

| Method                          | Complexity     | Best For                               | Requirements                   |
| ------------------------------- | -------------- | -------------------------------------- | ------------------------------ |
| **OAuth (Recommended)**         | ⚡ Easy        | Quick setup, most users                | GitHub account, VS Code        |
| **Personal Access Token (PAT)** | ⚡⚡ Moderate  | Advanced control, enterprise           | PAT with correct scopes        |
| **Local Docker**                | ⚡⚡⚡ Complex | Enterprise restrictions, local control | Docker, PAT, local environment |

## Method 1: Setup with OAuth (Recommended)

**Fastest and easiest method** - No Docker or config files needed

### Steps

| Step | Action                        | Details                                                             |
| ---- | ----------------------------- | ------------------------------------------------------------------- |
| 1    | Open Command Palette          | `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac)               |
| 2    | Add MCP Server                | Type `MCP: add server` → Press Enter                                |
| 3    | Select connection type        | Choose **HTTP (HTTP or Server-Sent Events)**                        |
| 4    | Enter Server URL              | `https://api.githubcopilot.com/mcp/` → Press Enter                  |
| 5    | Set Server ID                 | Press Enter for default OR type custom ID                           |
| 6    | Choose configuration location | **User settings** (all projects) OR **Workspace** (current project) |
| 7    | Authorize with GitHub         | Click **Allow** → Sign in to GitHub if prompted                     |

### Result

✅ **GitHub MCP Server ready to use** - Start using AI-powered tools to:

- Automate tasks
- Manage issues
- Analyze code directly in VS Code
- Stay focused while MCP handles background work

## Method 2: Setup with Personal Access Token (PAT)

**For advanced control and specific authentication needs**

### Prerequisites

| Requirement | Details                                      |
| ----------- | -------------------------------------------- |
| **PAT**     | Create with `repo` and `read:packages` scope |
| **Scopes**  | `repo`, `read:packages`                      |

### Steps

**1. Create PAT**:

- Go to GitHub → Settings → Developer settings → Personal access tokens
- Create new token with `repo` and `read:packages` scope

**2. Follow OAuth steps but cancel OAuth when prompted**

**3. Add headers to configuration file**:

```json
"headers": {
  "Authorization": "Bearer ${input:github_token}"
}
```

**4. Add input prompt for secure token entry**:

```json
"inputs": [
  {
    "id": "github_token",
    "type": "promptString",
    "description": "GitHub Personal Access Token",
    "password": true
  }
]
```

**5. Restart MCP server in VS Code**

**6. Enter PAT when prompted**

### Result

✅ **MCP server configured to use PAT for authorization**

## Method 3: Local MCP Server with Docker (Optional)

**For enterprises with GitHub Enterprise Server and PAT restrictions**

### When to Use

| Scenario                     | Should Use Local Docker Setup |
| ---------------------------- | ----------------------------- |
| **GitHub Enterprise Server** | ✅ Yes                        |
| **PAT restrictions**         | ✅ Yes                        |
| **All endpoints restricted** | ❌ Won't work (check admin)   |
| **Need local control**       | ✅ Yes                        |

### Requirements

| Requirement | Details                             |
| ----------- | ----------------------------------- |
| **Docker**  | Installed and running on system     |
| **PAT**     | Generated with necessary scopes     |
| **OAuth**   | NOT supported in local Docker setup |

### Steps

**1. Confirm Docker is installed and running**

**2. Generate PAT with necessary scopes**

**3. Use the following configuration**:

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

**4. Restart MCP server and enter PAT when prompted**

### Important Notes

⚠️ **Enterprise restrictions**: Can only access API scopes allowed by org policy
⚠️ **OAuth not supported**: Must use PAT for local Docker setup
⚠️ **Admin check**: If all endpoints restricted, MCP Server won't be available

## Configuration Location Options

| Location               | Scope           | When to Use                        |
| ---------------------- | --------------- | ---------------------------------- |
| **User settings**      | All projects    | Want MCP Server available globally |
| **Workspace settings** | Current project | Project-specific configuration     |

## Troubleshooting

### Common Issues & Solutions

| Issue                           | Check                    | Solution                                                            |
| ------------------------------- | ------------------------ | ------------------------------------------------------------------- |
| **Connection fails**            | GitHub account sign-in   | Confirm signed into GitHub in VS Code                               |
| **PAT authentication fails**    | PAT scopes and entry     | Ensure correct scopes (`repo`, `read:packages`) + entered correctly |
| **Configuration errors**        | Config file              | Double-check for typos or missing fields                            |
| **Docker setup fails**          | Docker status            | Ensure Docker installed and actively running                        |
| **Temporary connection issues** | VS Code/MCP Server state | Restart VS Code or MCP Server                                       |

### Troubleshooting Checklist

- [ ] Signed into GitHub account in VS Code
- [ ] PAT has correct scopes (if using PAT)
- [ ] PAT entered correctly (if using PAT)
- [ ] Configuration file has no typos
- [ ] Docker installed and running (if using Docker)
- [ ] Tried restarting VS Code
- [ ] Tried restarting MCP Server

## Setup Comparison Summary

| Aspect                 | OAuth          | PAT                  | Docker (Local)          |
| ---------------------- | -------------- | -------------------- | ----------------------- |
| **Ease of setup**      | ⚡ Easiest     | ⚡⚡ Moderate        | ⚡⚡⚡ Complex          |
| **Configuration**      | Minimal        | Config file edits    | Docker + config         |
| **Authentication**     | One-click      | Manual token entry   | Manual token entry      |
| **Requirements**       | GitHub account | PAT creation         | Docker + PAT            |
| **Enterprise support** | ✅ Yes         | ✅ Yes               | ✅ Yes                  |
| **OAuth available**    | ✅ Yes         | ❌ No (cancel OAuth) | ❌ No                   |
| **Best for**           | Most users     | Advanced control     | Enterprise restrictions |

## Quick Start Guide

**For most users (OAuth)**:

```
Command Palette → MCP: add server → HTTP →
https://api.githubcopilot.com/mcp/ → Allow GitHub
```

**For advanced users (PAT)**:

```
1. Create PAT with repo + read:packages
2. Same as OAuth but cancel authorization
3. Add headers + inputs to config
4. Restart + enter PAT
```

**For enterprises (Docker)**:

```
1. Confirm Docker running
2. Generate PAT
3. Add Docker config
4. Restart + enter PAT
```

## Key Takeaways

✅ **OAuth is fastest**: One-click setup, no config files needed
✅ **PAT for control**: Advanced authentication with specific scopes
✅ **Docker for enterprises**: Local setup with PAT restrictions
✅ **Two config locations**: User (all projects) or Workspace (current project)
✅ **Easy troubleshooting**: Check sign-in, PAT scopes, Docker status, restart
✅ **Ready to use**: After setup, access 30+ tools directly in VS Code
⚠️ **Enterprise note**: Check with admin if endpoints restricted

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/mcp-server/3-configure-connect)

# Using GitHub MCP Server with Copilot Chat

## Overview

Combine MCP servers with Copilot's **agentic mode** to move beyond prompts and enable true collaboration where Copilot can plan, execute, and refine workflows.

**You'll learn**:

- What Copilot's agentic mode is and how it differs from standard use
- How MCP servers enhance agent mode
- Key benefits of combining MCP with agent mode
- Best practices for agentic workflows

## How to Use GitHub MCP Server with Copilot Chat

### Quick Setup (4 Steps)

| Step | Action                       | What to Do                                    |
| ---- | ---------------------------- | --------------------------------------------- |
| 1    | Open Copilot Chat in VS Code | Access Copilot Chat panel                     |
| 2    | Switch to Agent mode         | Activates MCP Server tools                    |
| 3    | Click "Select tools"         | View all available MCP Server functionalities |
| 4    | Use natural language prompts | Create issues, summarize repos, get insights  |

### What You Can Do

**Example tasks**:

- ✅ Create new issues
- ✅ Summarize repositories
- ✅ Get insights into your work
- ✅ Automate workflows
- ✅ Manage tasks across platforms

## What Are Agentic Capabilities?

**Agentic capabilities** = Copilot acting as autonomous collaborator, not just responsive assistant

### Three Core Abilities

| Capability             | What It Means                                               |
| ---------------------- | ----------------------------------------------------------- |
| **Work independently** | Carries out multi-step workflows without constant guidance  |
| **Make decisions**     | Chooses which tools/approaches to use based on context      |
| **Adapt and improve**  | Responds to feedback, adjusts approach, iterates on results |

**Analogy**: Like having a teammate who understands the bigger picture, not just following individual instructions

## Copilot Standard Use vs. Agent Mode

| Aspect              | Standard Copilot      | Agent Mode (Agentic)                 |
| ------------------- | --------------------- | ------------------------------------ |
| **Interaction**     | Responsive to prompts | Autonomous collaborator              |
| **Workflow**        | Single-step responses | Multi-step workflows                 |
| **Decision-making** | Follows instructions  | Chooses tools and approaches         |
| **Iteration**       | Manual                | Automatic adaptation and improvement |
| **Scope**           | Immediate task        | Understands bigger picture           |

## How MCP Makes Agent Mode Stronger

**Agent mode alone** = Powerful
**Agent mode + MCP** = Reaches beyond immediate coding environment

### What MCP Adds to Agent Mode

| Enhancement                | What It Enables                                                  |
| -------------------------- | ---------------------------------------------------------------- |
| **External data access**   | Access external data, APIs, enterprise tools directly            |
| **Cross-platform context** | Stay in context across multiple platforms (no app switching)     |
| **Agentic loops**          | Dynamically seek info, analyze results, make informed next steps |
| **Continuous refinement**  | Explore, adapt, refine until desired outcome achieved            |

### Agentic Loops Explained

**Traditional workflow**: Prompt → Response → Done

**Agentic loop with MCP**:

```
1. Receive task
2. Seek information (via MCP tools)
3. Analyze results
4. Make informed next steps
5. Iterate and refine
6. Produce outcome
```

**Result**: Copilot works in a **cycle** of exploring, adapting, and refining (not just reacting to a single prompt)

## Benefits of Combining MCP with Agent Mode

### Three Key Advantages

| Benefit                   | What You Get                                             | Impact                          |
| ------------------------- | -------------------------------------------------------- | ------------------------------- |
| **Extended context**      | Draw on information from multiple systems                | Not limited to code editor      |
| **Reduced manual effort** | Automate routine work (issues, workflows, checks)        | Focus on higher-value decisions |
| **Seamless integration**  | Tasks span tools and platforms without custom connectors | No constant app switching       |

### Detailed Benefits

**Extended Context**:

- Access GitHub issues
- Query external APIs
- Pull data from enterprise tools
- Maintain context across all sources

**Reduced Manual Effort**:

- Opening issues → Automated
- Managing workflows → Automated
- Running checks → Automated
- You focus on → Strategic decisions

**Seamless Integration**:

- No custom connectors needed
- No constant switching between tools
- Copilot handles cross-platform coordination
- Single interface for complex workflows

## Best Practices for Success

### 5 Strategies for Maximum Effectiveness

| Practice                    | How to Apply                                        | Why It Matters                             |
| --------------------------- | --------------------------------------------------- | ------------------------------------------ |
| **1. Be clear about goals** | Define what you want + final output                 | Copilot understands success criteria       |
| **2. Provide context**      | Share background, links, references, prior steps    | Better decisions with more information     |
| **3. Set boundaries**       | State if you want planning only (not changes yet)   | Control scope of autonomous actions        |
| **4. Ask for confirmation** | Have Copilot summarize plan before big changes      | Human approval gate before execution       |
| **5. Use prompt files**     | Create custom prompt files for specific MCP servers | Consistent behavior aligned with workflows |

### Best Practice Examples

**Clear Goals**:

```
❌ Bad: "Help with the project"
✅ Good: "Create 3 unit tests for UserService.validate() covering success, failure, and edge cases"
```

**Provide Context**:

```
❌ Bad: "Fix this"
✅ Good: "Fix this authentication bug. Context: We use JWT tokens, issue started after PR #123, affects mobile users only"
```

**Set Boundaries**:

```
❌ Bad: "Update the database schema"
✅ Good: "Plan database schema changes for user preferences feature. Show me the plan before making any changes"
```

**Ask for Confirmation**:

```
❌ Bad: "Refactor the entire codebase"
✅ Good: "Summarize your refactoring plan for the auth module. Wait for my approval before proceeding"
```

**Use Prompt Files**:

- Create `.github/copilot-instructions.md`
- Define how to behave with specific MCP servers
- Keeps behavior consistent
- Aligns with team workflows

## Workflow Comparison

### Traditional Workflow (Without Agent Mode + MCP)

```
1. You: Write prompt
2. Copilot: Suggest code
3. You: Apply suggestion
4. You: Switch to GitHub
5. You: Create issue manually
6. You: Switch back to VS Code
7. You: Continue coding
```

### Agentic Workflow (With Agent Mode + MCP)

```
1. You: "Create issue for this bug and add it to sprint backlog"
2. Copilot:
   - Analyzes bug
   - Creates GitHub issue
   - Adds to project board
   - Updates sprint backlog
   - Returns to you with confirmation
3. You: Continue coding (never left VS Code)
```

## Controlling MCP Tools

**You have control over which tools are active**:

| Control Method        | How                                   | Use Case                      |
| --------------------- | ------------------------------------- | ----------------------------- |
| **Select tools**      | Click "Select tools" in Agent mode    | Choose specific MCP tools     |
| **Limit tool access** | Configure which tools Copilot can use | Restrict to safe/needed tools |
| **Set boundaries**    | State limitations in prompt           | "Only analyze, don't modify"  |

## Use Case Examples

| Task                       | Without MCP + Agent      | With MCP + Agent                     |
| -------------------------- | ------------------------ | ------------------------------------ |
| **Create issue from bug**  | Manual GitHub navigation | "Create issue" → Done                |
| **Summarize repo**         | Read files manually      | "Summarize repo" → Complete overview |
| **Triage multiple issues** | Review each manually     | "Rank by priority" → Sorted list     |
| **Cross-repo insights**    | Switch between repos     | "Compare approaches" → Analysis      |

## Agent Mode + MCP = Autonomous Collaboration

### The Power of Combination

**Agent Mode** provides:

- Autonomous decision-making
- Multi-step workflows
- Iterative refinement

**MCP** provides:

- External data access
- Cross-platform reach
- Enterprise tool integration

**Together** = Truly autonomous AI collaborator that:

- ✅ Understands context from multiple sources
- ✅ Makes informed decisions
- ✅ Executes across platforms
- ✅ Iterates until successful
- ✅ Stays aligned with your goals

## Key Advantages Summary

| Advantage                 | Benefit                                    |
| ------------------------- | ------------------------------------------ |
| **Autonomous workflows**  | Multi-step tasks without constant guidance |
| **Informed decisions**    | Access to external data and tools          |
| **Cross-platform power**  | No app switching needed                    |
| **Iterative improvement** | Explores, adapts, refines automatically    |
| **Extended context**      | Information from multiple systems          |
| **Reduced manual work**   | Automation of routine tasks                |
| **Seamless integration**  | Tasks span tools without custom connectors |

## Quick Reference: Agent Mode with MCP

**Setup**:

```
1. Open Copilot Chat
2. Switch to Agent mode
3. Click "Select tools"
4. Use natural language
```

**Best practices**:

```
✅ Clear goals
✅ Provide context
✅ Set boundaries
✅ Ask for confirmation
✅ Use prompt files
```

**What you get**:

```
✅ Multi-step workflows
✅ External data access
✅ Cross-platform tasks
✅ Iterative refinement
✅ Autonomous collaboration
```

## Key Takeaways

✅ **Agentic mode = Autonomous collaboration**: Copilot acts as teammate, not just assistant
✅ **3 core abilities**: Work independently, make decisions, adapt and improve
✅ **MCP enhances agent mode**: Adds external data, cross-platform context, agentic loops
✅ **3 key benefits**: Extended context, reduced manual effort, seamless integration
✅ **Agentic loops**: Explore → Analyze → Refine → Produce outcome (not just single prompt)
✅ **Best practices**: Clear goals, context, boundaries, confirmation, prompt files
✅ **Control**: You choose which MCP tools are active and set limits
✅ **Real collaboration**: Understands bigger picture, makes informed decisions
✅ **Cross-platform power**: Work across GitHub, APIs, enterprise tools without switching
⚠️ **Human oversight**: Always review plans before big changes

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/mcp-server/4-use-github-copilot-chat)
