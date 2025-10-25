# What is GitHub Copilot

## Overview

**The Problem**: When writing code, you often:

- Consult documentation or web pages to remember syntax
- Spend hours fixing issues
- Write tests manually
- Create documentation
- Use code snippets or IDE tools

**The Question**: Is there a better way?

**The Solution**: GitHub Copilot - AI assistant from within your IDE

## What is GitHub Copilot?

**Definition**: AI assistant that you use from within your IDE, capable of generating code and much more

**Key capabilities**:

| Capability           | What It Does                                |
| -------------------- | ------------------------------------------- |
| **Code generation**  | Creates code based on prompts               |
| **Natural language** | Understands plain language instructions     |
| **Context-aware**    | Provides suggestions based on what you type |
| **Interactive**      | Accept or reject suggestions                |

## How Does It Work?

### Prompt-Based System

**Input**: You provide a prompt (natural language instruction)

**Processing**: GitHub Copilot analyzes your prompt

**Output**: Generates code suggestions you can accept or reject

### Example: Web API Creation

**Your prompt** (as a comment in code file):

```javascript
// Create a web API using express and JavaScript with routes for products and customers
```

**Copilot's response**:

```javascript
const express = require("express");

app = express();
app.path("/products", () => "products");
app.listen(3000, () => "app runs");
```

**Your choice**: Accept or reject the suggestion

## How Copilot Recognizes Prompts

### Two Ways to Provide Prompts

| Method                 | How It Works                                  | Example File Types           |
| ---------------------- | --------------------------------------------- | ---------------------------- |
| **Code file comments** | Type as comment in code file                  | `.py`, `.js`, `.ts`, `.java` |
| **Markdown file text** | Type text and wait a few seconds for response | `.md`                        |

### Example Prompts in Different Formats

**JavaScript comment**:

```javascript
// Function to validate email address
```

**Python comment**:

```python
# Create a class for user authentication
```

**Markdown file**:

```markdown
Write a function that calculates compound interest
```

## Accepting Suggestions

### How Suggestions Appear

**Visual indicator**: Grey text (if you use black as your text color)

**Action**: Press `Tab` key to accept

### Suggestion Navigation

| Action                    | Shortcut (Windows/Linux) | Shortcut (Mac)      |
| ------------------------- | ------------------------ | ------------------- |
| **Accept suggestion**     | `Tab`                    | `Tab`               |
| **Cycle through options** | `Ctrl+Enter`             | `Cmd+Enter`         |
| **Select best option**    | Navigate and choose      | Navigate and choose |

### Multiple Suggestions

**Feature**: Copilot might suggest multiple options

**How to use**:

1. Press `Ctrl+Enter` (or `Cmd+Enter` on Mac)
2. View various suggestions
3. Select the most appropriate one

## Key Characteristics

| Aspect               | Details                          |
| -------------------- | -------------------------------- |
| **Location**         | Works within your IDE            |
| **Input method**     | Natural language prompts         |
| **Output format**    | Code suggestions                 |
| **Control**          | You decide to accept or reject   |
| **Multiple options** | Can provide several alternatives |

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-javascript/2-what-is-github-copilot)

# Using GitHub Copilot with JavaScript

## Overview

**Focus**: How Copilot helps with existing projects and complicated tasks

**Key areas**:

- Keeping code fresh and updated
- Fixing bugs
- Adding new features
- Improving functionality and usability

## Developing with GitHub Copilot

### Common Development Needs

| Need                  | What It Involves            | Copilot's Role          |
| --------------------- | --------------------------- | ----------------------- |
| **Keep code updated** | Continuous maintenance      | Suggest modern patterns |
| **Fix bugs**          | Debug and resolve issues    | Propose fixes           |
| **Add features**      | Implement new functionality | Generate feature code   |
| **Improve usability** | Enhance user experience     | Suggest UX improvements |

### GitHub Copilot Chat

**What it is**: Interactive chat interface for code-related questions

**Use cases**:

- Ask code questions
- Receive code-related answers
- Discuss implementation approaches
- Get explanations

**Difference from inline**:

| Feature         | Inline Copilot   | Copilot Chat              |
| --------------- | ---------------- | ------------------------- |
| **Format**      | Code suggestions | Conversational interface  |
| **Use for**     | As you type      | Complex questions         |
| **Interaction** | Accept/reject    | Back-and-forth discussion |

## Prompt Engineering

### What is a Prompt?

**Definition**: A collection of instructions or guidelines that help generate code

**Purpose**: Generate specific responses from Copilot

**Formats**:

- Comment in code file
- Input in GitHub Copilot Chat
- Code that Copilot autocompletes

### Quality of Output

**Key principle**: Quality of Copilot's output depends on how well you craft your prompt

**Essential**: Creating an effective prompt is essential for achieving desired outcomes

### Poor Prompt Example

❌ **Vague and ambiguous**:

```javascript
// Create an API endpoint
```

**Problems with this prompt**:

- Could use unknown framework
- Might require unrecognized data
- Ambiguous about requirements
- No clear scope

**Result**: Copilot might not give you what you need

### Good Prompt Example

✅ **Specific, clear, and scoped**:

```javascript
// Create an API endpoint using the React framework that accepts a JSON payload in a POST request
```

**Why this works**:

- Specifies framework (React)
- States data format (JSON payload)
- Defines HTTP method (POST request)
- Clear goal and scope

**Result**: Copilot understands exactly what you need

### Prompt Quality Comparison

| Aspect          | Poor Prompt              | Good Prompt                                                        |
| --------------- | ------------------------ | ------------------------------------------------------------------ |
| **Clarity**     | ❌ Vague                 | ✅ Clear                                                           |
| **Specificity** | ❌ Ambiguous             | ✅ Specific                                                        |
| **Scope**       | ❌ Undefined             | ✅ Well-defined                                                    |
| **Context**     | ❌ Missing details       | ✅ Includes framework, method, data format                         |
| **Example**     | "Create an API endpoint" | "Create API endpoint using React framework accepting JSON in POST" |
| **Result**      | ❌ May not meet needs    | ✅ Generates appropriate code                                      |

## Best Practices Using GitHub Copilot

### Core Principle

**Copilot supercharges productivity** but requires good practices to ensure quality

### Practice 1: Start Simple, Then Elaborate

**Strategy**: Begin with simple prompts, then add more elaborate components as you go

#### Example: Building an HTML Form

**Step 1 - Simple prompt**:

```text
create an HTML form with a text field and button
```

**What you get**: Basic form structure

**Step 2 - Elaborate**:

```text
Add an event listener to the button to send a POST request to /generate endpoint and display response in a div with id "result"
```

**What you get**: Form with functionality, event handling, and response display

#### Progressive Elaboration Benefits

| Approach               | Benefit                       |
| ---------------------- | ----------------------------- |
| **Start simple**       | Get foundation quickly        |
| **Add incrementally**  | Build complexity step-by-step |
| **Specific additions** | Control what gets added       |
| **Clear scope**        | Each step has clear goal      |

### Practice 2: Cycle Between Suggestions

**How to do it**:

- Press `Ctrl+Enter` (Windows/Linux) or `Cmd+Enter` (Mac)
- View various suggestions from Copilot
- Pick the best output

**Alternative**: Use GitHub Copilot Chat

- Use chat input to add your prompt
- Interact with the output
- Refine through conversation

### Practice 3: Reword or Start Writing

**If you're stuck or not getting results you want**:

| Strategy               | When to Use                  | How It Helps                      |
| ---------------------- | ---------------------------- | --------------------------------- |
| **Reword the prompt**  | Suggestion isn't quite right | New perspective, better results   |
| **Start writing code** | Want Copilot to autocomplete | Gives Copilot context to build on |

### Best Practices Summary Table

| Practice                       | How To                                 | Why It Matters                  |
| ------------------------------ | -------------------------------------- | ------------------------------- |
| **Start simple, elaborate**    | Begin basic, add details incrementally | Build complexity systematically |
| **Cycle suggestions**          | Use `Ctrl+Enter` to view options       | Find best implementation        |
| **Use chat for complex tasks** | Switch to Copilot Chat interface       | Better for discussions          |
| **Reword if stuck**            | Try different phrasing                 | Different angle, better results |
| **Start writing**              | Write code for Copilot to complete     | Provides context                |

## Context Awareness: Open Files

### How Copilot Uses Context

**Important**: GitHub Copilot uses open files in your text editor as additional context

**Why this matters**: Provides useful information beyond the prompt or code you're writing

### Providing Additional Context

**Method 1 - Open relevant files**:

```
If you need suggestions based on other files:
→ Open those files in your editor
→ Copilot will consider their content
```

**Method 2 - Use `@workspace` with Copilot Chat**:

```
@workspace How can I refactor this authentication logic to match the patterns used in the project?
```

### Context Strategy

| Scenario                            | Strategy                        | Tool                |
| ----------------------------------- | ------------------------------- | ------------------- |
| **Single file work**                | Just work in that file          | Inline Copilot      |
| **Multiple file context needed**    | Open related files              | Inline Copilot      |
| **Project-wide context needed**     | Use `@workspace`                | GitHub Copilot Chat |
| **Need to reference specific file** | Open it or use `#file:filename` | Both                |

## JavaScript-Specific Examples

### Example 1: Express API Creation

**Prompt**:

```javascript
// Create a web API using express and JavaScript with routes for products and customers
```

**Copilot generates**:

```javascript
const express = require("express");

app = express();
app.path("/products", () => "products");
app.listen(3000, () => "app runs");
```

### Example 2: Progressive Form Building

**Step 1 prompt**:

```text
create an HTML form with a text field and button
```

**Copilot generates**:

```html
<form>
  <input type="text" id="textField" name="textField" />
  <button type="submit">Submit</button>
</form>
```

**Step 2 prompt**:

```text
Add an event listener to the button to send a POST request to /generate endpoint and display response in a div with id "result"
```

**Copilot generates**:

```javascript
document.querySelector("button").addEventListener("click", async (e) => {
  e.preventDefault();
  const response = await fetch("/generate", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ text: document.getElementById("textField").value }),
  });
  const data = await response.json();
  document.getElementById("result").innerHTML = data;
});
```

### Example 3: API Endpoint with Specifics

**Poor prompt**:

```javascript
// Create an API endpoint
```

**Better prompt**:

```javascript
// Create an API endpoint using the React framework that accepts a JSON payload in a POST request
```

**Best prompt** (even more specific):

```javascript
// Create an Express API endpoint at /api/users that accepts a POST request
// with JSON payload containing username and email fields
// Validate the data and return 400 if invalid, 201 if created successfully
```

## Prompt Engineering Patterns for JavaScript

### Pattern 1: Framework-Specific

```javascript
// Create a [framework] [component] that [does what]
// Example:
// Create a React component that displays a list of products with filtering
```

### Pattern 2: Functionality-Specific

```javascript
// Function to [action] [object] using [method/library]
// Example:
// Function to validate email addresses using regex patterns
```

### Pattern 3: Integration-Specific

```javascript
// Connect to [service] and [action] using [library]
// Example:
// Connect to MongoDB database and fetch user data using mongoose
```

### Pattern 4: Progressive Elaboration

```javascript
// Step 1: Basic structure
// Create an HTML form

// Step 2: Add functionality
// Add submit handler

// Step 3: Add validation
// Validate email format before submission

// Step 4: Add error handling
// Display error messages for invalid inputs
```

## Common JavaScript Tasks with Copilot

| Task                    | Prompt Example                                 | What Copilot Generates               |
| ----------------------- | ---------------------------------------------- | ------------------------------------ |
| **API creation**        | "Create Express API with user routes"          | Complete Express setup with routes   |
| **Form handling**       | "Add form validation for email and password"   | Validation logic with error handling |
| **Async operations**    | "Fetch data from API and handle errors"        | Async/await with try-catch           |
| **DOM manipulation**    | "Add event listener to update div content"     | Event handling code                  |
| **Data transformation** | "Convert array of objects to CSV format"       | Transformation function              |
| **Testing**             | "Write Jest tests for authentication function" | Test suite with multiple cases       |

## Workflow Integration

### Typical Development Workflow with Copilot

```
1. Write comment describing what you need
   ↓
2. Copilot suggests implementation
   ↓
3. Review suggestion (press Ctrl+Enter for alternatives)
   ↓
4. Accept (Tab) or refine prompt
   ↓
5. Elaborate with more specific requirements
   ↓
6. Iterate until complete
```

### When to Use Each Feature

| Feature            | When to Use                    | Example Scenario                         |
| ------------------ | ------------------------------ | ---------------------------------------- |
| **Inline Copilot** | Writing new code, autocomplete | Creating functions, adding features      |
| **Copilot Chat**   | Complex questions, discussions | "How should I structure this API?"       |
| **@workspace**     | Project-wide context needed    | "Update all API calls to use new format" |
| **#file**          | Reference specific file        | "Refactor based on patterns in utils.js" |

## Quick Reference: JavaScript with Copilot

### Basic Usage

```javascript
// [Description of what you want]
// Example: Create a function to calculate total price with tax
```

### Accept/Navigate Suggestions

- **Accept**: `Tab`
- **View alternatives**: `Ctrl+Enter` (or `Cmd+Enter`)
- **Reject**: Keep typing or `Esc`

### Best Prompt Structure

```javascript
// [Action] [object] using [method/framework] that [specific requirements]
// Example: Create Express middleware using JWT that validates user tokens
```

### Progressive Elaboration

```
Step 1: Basic → "create HTML form"
Step 2: Add details → "add text field and button"
Step 3: Add behavior → "add event listener for submit"
Step 4: Add validation → "validate input before submit"
```

## Key Takeaways

✅ **AI assistant in IDE**: GitHub Copilot generates code based on natural language prompts
✅ **Prompt recognition**: Works with code comments (`.js`, `.py`) and markdown text
✅ **Accept suggestions**: Press `Tab` to accept, `Ctrl+Enter` to cycle through options
✅ **Prompt quality matters**: Specific, clear prompts generate better code
✅ **Progressive elaboration**: Start simple, add complexity incrementally
✅ **Multiple suggestions**: Use `Ctrl+Enter` to view and select best option
✅ **Context awareness**: Copilot uses open files; use `@workspace` for project context
✅ **Chat for complexity**: Use GitHub Copilot Chat for complex questions and discussions
✅ **Reword if stuck**: Try different phrasing or start writing code to autocomplete
✅ **JavaScript-specific**: Works great for Express APIs, React components, async operations
⚠️ **Vague prompts fail**: Ambiguous prompts like "Create an API endpoint" yield poor results
⚠️ **Specificity wins**: Include framework, method, data format, and requirements in prompts

📚 [What is GitHub Copilot](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-javascript/2-what-is-github-copilot) | [Use Copilot with JavaScript](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-javascript/4-use-copilot-with-javascript)
