# What is GitHub Copilot?

## Overview

**The Problem**: When writing code, you often:

- Consult official documentation or web pages to remember syntax
- Spend hours trying to resolve problems when code isn't working
- Write tests and documentation manually
- Use code snippets or IDE tools

**The Question**: Is there a better way?

**The Solution**: GitHub Copilot - AI assistant from within your IDE

## What is GitHub Copilot?

**Definition**: AI assistant that you use from within your IDE, capable of generating code and much more

**Key capabilities**:

| Capability           | What It Does                                |
| -------------------- | ------------------------------------------- |
| **Code generation**  | Creates code based on prompts               |
| **Natural language** | Uses prompts (natural language text)        |
| **Context-aware**    | Provides suggestions based on what you type |
| **Interactive**      | Accept or reject suggestions                |

## How Does It Work?

### Prompt-Based System

**Input**: You provide a prompt (natural language text)

**Processing**: GitHub Copilot analyzes your prompt

**Output**: Generates code suggestions you can accept or reject

### Example: FastAPI Web API Creation

**Your prompt** (as a comment in Python file):

```python
# Create a web API using FastAPI with a route to products.
```

**Copilot's response**:

```python
from fastapi import FastAPI
app = FastAPI()

@app.get("/products")
def read_products():
    return []
```

**Your choice**: Accept or reject the suggestion

## How Copilot Recognizes Prompts

### Two Ways to Provide Prompts

| Method                 | How It Works                                  | Example File Types            |
| ---------------------- | --------------------------------------------- | ----------------------------- |
| **Code file comments** | Type as comment in code file                  | `.py`, `.js`, `.java`, `.cpp` |
| **Markdown file text** | Type text and wait a few seconds for response | `.md`                         |

### Example Prompts in Different Formats

**Python comment**:

```python
# Create a function to validate email addresses
```

**JavaScript comment**:

```javascript
// Create a REST API endpoint
```

**Markdown file**:

```markdown
Write a Python function that calculates compound interest
```

## Accepting Suggestions

### How Suggestions Appear

**Visual indicator**: Grey text (gray code if you use black as your text color)

**Action**: Press `Tab` key to accept

### Suggestion Navigation

| Action                    | Shortcut (Windows/Linux) | Shortcut (Mac)      |
| ------------------------- | ------------------------ | ------------------- |
| **Accept suggestion**     | `Tab`                    | `Tab`               |
| **Cycle through options** | `Ctrl+Enter`             | `Cmd+Enter`         |
| **Select best option**    | Navigate and choose      | Navigate and choose |

### Multiple Suggestions

**Feature**: Copilot might suggest more than one thing

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

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/2-what-is-github-copilot)

# Use GitHub Copilot with Python

## Overview

**Focus**: How Copilot helps with existing projects and complicated tasks

**Key areas**:

- Keeping code fresh and updated
- Fixing bugs
- Adding new features
- Improving functionality and usability

## Developing with GitHub Copilot

### Common Development Needs

| Need                  | What It Involves            | Copilot's Role                 |
| --------------------- | --------------------------- | ------------------------------ |
| **Keep code updated** | Continuous maintenance      | Suggest modern Python patterns |
| **Fix bugs**          | Debug and resolve issues    | Propose fixes                  |
| **Add features**      | Implement new functionality | Generate feature code          |
| **Improve usability** | Enhance user experience     | Suggest improvements           |

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

**Crucial**: Designing an effective prompt is crucial to ensuring you achieve your desired outcome

### Poor Prompt Example

❌ **Vague and ambiguous**:

```python
# Create an API endpoint
```

**Problems with this prompt**:

- Could use unknown framework
- Might require unrecognized data
- Ambiguous about requirements
- No clear scope

**Result**: Copilot might not give you what you need

### Good Prompt Example

✅ **Specific, clear, and scoped**:

```python
# Create an API endpoint using the FastAPI framework that accepts a JSON payload in a POST request
```

**Why this works**:

- Specifies framework (FastAPI)
- States data format (JSON payload)
- Defines HTTP method (POST request)
- Clear goal and scope

**Result**: Copilot understands exactly what you need

### Prompt Quality Comparison

| Aspect          | Poor Prompt              | Good Prompt                                                |
| --------------- | ------------------------ | ---------------------------------------------------------- |
| **Clarity**     | ❌ Vague                 | ✅ Clear                                                   |
| **Specificity** | ❌ Ambiguous             | ✅ Specific                                                |
| **Scope**       | ❌ Undefined             | ✅ Well-defined                                            |
| **Context**     | ❌ Missing details       | ✅ Includes framework, method, data format                 |
| **Example**     | "Create an API endpoint" | "Create API endpoint using FastAPI accepting JSON in POST" |
| **Result**      | ❌ May not meet needs    | ✅ Generates appropriate code                              |

## Best Practices Using GitHub Copilot

### Core Principle

**Copilot supercharges productivity** but requires good practices to ensure quality

### Practice 1: Start Simple, Then Elaborate

**Strategy**: Keep prompts simple, then add more elaborate components as you keep going

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

**If you're not getting results you want**:

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

**Why this matters**: Provides useful information in addition to the prompt or code you're writing

### Providing Additional Context

**Method 1 - Open relevant files**:

```
If you need suggestions based on other files:
→ Open those files in your editor
→ Copilot will consider their content
```

**Method 2 - Use `@workspace` with Copilot Chat**:

```
@workspace How can I refactor this Flask authentication to match the patterns used in the project?
```

### Context Strategy

| Scenario                            | Strategy                        | Tool                |
| ----------------------------------- | ------------------------------- | ------------------- |
| **Single file work**                | Just work in that file          | Inline Copilot      |
| **Multiple file context needed**    | Open related files              | Inline Copilot      |
| **Project-wide context needed**     | Use `@workspace`                | GitHub Copilot Chat |
| **Need to reference specific file** | Open it or use `#file:filename` | Both                |

## Python-Specific Examples

### Example 1: FastAPI Web API Creation

**Prompt**:

```python
# Create a web API using FastAPI with a route to products.
```

**Copilot generates**:

```python
from fastapi import FastAPI
app = FastAPI()

@app.get("/products")
def read_products():
    return []
```

### Example 2: Progressive API Development

**Step 1 prompt**:

```python
# Create a FastAPI endpoint for user registration
```

**Copilot generates**:

```python
@app.post("/register")
def register_user(user: dict):
    return {"message": "User registered"}
```

**Step 2 prompt**:

```python
# Add email validation and password hashing to the registration endpoint
```

**Copilot generates**:

```python
from pydantic import BaseModel, EmailStr
from passlib.context import CryptContext

pwd_context = CryptContext(schemes=["bcrypt"], deprecated="auto")

class UserRegistration(BaseModel):
    email: EmailStr
    password: str

@app.post("/register")
def register_user(user: UserRegistration):
    hashed_password = pwd_context.hash(user.password)
    return {"message": "User registered", "email": user.email}
```

### Example 3: API Endpoint with Specifics

**Poor prompt**:

```python
# Create an API endpoint
```

**Better prompt**:

```python
# Create an API endpoint using the FastAPI framework that accepts a JSON payload in a POST request
```

**Best prompt** (even more specific):

```python
# Create a FastAPI endpoint at /api/users that accepts a POST request
# with JSON payload containing username and email fields
# Use Pydantic models for validation
# Return 400 if invalid, 201 if created successfully
```

## Prompt Engineering Patterns for Python

### Pattern 1: Framework-Specific

```python
# Create a [framework] [component] that [does what]
# Example:
# Create a Flask route that handles user authentication with JWT tokens
```

### Pattern 2: Functionality-Specific

```python
# Function to [action] [object] using [method/library]
# Example:
# Function to validate email addresses using regex and handle exceptions
```

### Pattern 3: Data Processing

```python
# Process [data type] and [action] using [library]
# Example:
# Process CSV file and extract columns using pandas with error handling
```

### Pattern 4: Progressive Elaboration

```python
# Step 1: Basic structure
# Create a class for user management

# Step 2: Add methods
# Add methods for create, read, update, delete operations

# Step 3: Add validation
# Add input validation using Pydantic models

# Step 4: Add error handling
# Add try-except blocks for database operations
```

## Common Python Tasks with Copilot

| Task                    | Prompt Example                                           | What Copilot Generates             |
| ----------------------- | -------------------------------------------------------- | ---------------------------------- |
| **API creation**        | "Create FastAPI app with CRUD operations for users"      | Complete FastAPI setup with routes |
| **Data validation**     | "Add Pydantic models for user data validation"           | Pydantic model classes             |
| **Database operations** | "Connect to PostgreSQL using SQLAlchemy"                 | Database setup and connection      |
| **Data processing**     | "Read CSV file with pandas and clean missing values"     | Data processing pipeline           |
| **Async operations**    | "Create async function to fetch data from multiple APIs" | Async/await with aiohttp           |
| **Testing**             | "Write pytest tests for authentication function"         | Test suite with fixtures           |

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

| Feature            | When to Use                    | Example Scenario                          |
| ------------------ | ------------------------------ | ----------------------------------------- |
| **Inline Copilot** | Writing new code, autocomplete | Creating functions, adding features       |
| **Copilot Chat**   | Complex questions, discussions | "How should I structure this Flask app?"  |
| **@workspace**     | Project-wide context needed    | "Update all API routes to async"          |
| **#file**          | Reference specific file        | "Refactor based on patterns in models.py" |

## Python-Specific Prompt Examples

### Example 1: Data Science

**Prompt**:

```python
# Load CSV file using pandas and create a scatter plot showing correlation between age and income
```

**Copilot generates**:

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('data.csv')
plt.scatter(df['age'], df['income'])
plt.xlabel('Age')
plt.ylabel('Income')
plt.title('Age vs Income Correlation')
plt.show()
```

### Example 2: Web Scraping

**Prompt**:

```python
# Create a function using BeautifulSoup to scrape product titles from an e-commerce website
# Handle connection errors and missing elements gracefully
```

**Copilot generates**:

```python
from bs4 import BeautifulSoup
import requests

def scrape_product_titles(url):
    try:
        response = requests.get(url, timeout=10)
        response.raise_for_status()
        soup = BeautifulSoup(response.content, 'html.parser')
        titles = [title.text.strip() for title in soup.find_all('h2', class_='product-title')]
        return titles
    except requests.RequestException as e:
        print(f"Error fetching data: {e}")
        return []
```

### Example 3: Machine Learning

**Prompt**:

```python
# Create a simple neural network using TensorFlow for binary classification
# Include data preprocessing and model evaluation
```

**Copilot generates**:

```python
import tensorflow as tf
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

# Preprocessing
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# Model
model = tf.keras.Sequential([
    tf.keras.layers.Dense(64, activation='relu', input_shape=(X_train.shape[1],)),
    tf.keras.layers.Dropout(0.2),
    tf.keras.layers.Dense(32, activation='relu'),
    tf.keras.layers.Dense(1, activation='sigmoid')
])

model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
model.fit(X_train, y_train, epochs=10, validation_split=0.2)
```

## Quick Reference: Python with Copilot

### Basic Usage

```python
# [Description of what you want]
# Example: Create a function to calculate factorial recursively
```

### Accept/Navigate Suggestions

- **Accept**: `Tab`
- **View alternatives**: `Ctrl+Enter` (or `Cmd+Enter`)
- **Reject**: Keep typing or `Esc`

### Best Prompt Structure

```python
# [Action] [object] using [method/framework] that [specific requirements]
# Example: Create FastAPI middleware using JWT that validates user tokens and handles expired tokens
```

### Progressive Elaboration

```
Step 1: Basic → "create FastAPI endpoint"
Step 2: Add details → "add Pydantic model for validation"
Step 3: Add behavior → "add error handling for invalid input"
Step 4: Add database → "save to PostgreSQL using SQLAlchemy"
```

## Python Framework Examples

### FastAPI Patterns

```python
# Create a FastAPI endpoint that [action]
# Use Pydantic for [validation needs]
# Handle [error scenarios]
```

### Flask Patterns

```python
# Create a Flask route that [action]
# Use Flask-SQLAlchemy for [database operations]
# Include error handling for [scenarios]
```

### Django Patterns

```python
# Create a Django view that [action]
# Use Django ORM for [database operations]
# Include permissions check for [user roles]
```

### Data Science Patterns

```python
# Load [data source] using [library]
# Perform [analysis/transformation]
# Visualize results using [plotting library]
```

## Key Takeaways

✅ **AI assistant in IDE**: GitHub Copilot generates Python code based on natural language prompts
✅ **Prompt recognition**: Works with code comments (`.py`) and markdown text
✅ **Accept suggestions**: Press `Tab` to accept, `Ctrl+Enter` to cycle through options
✅ **Prompt quality matters**: Specific, clear prompts generate better code
✅ **Progressive elaboration**: Start simple, add complexity incrementally
✅ **Multiple suggestions**: Use `Ctrl+Enter` to view and select best option
✅ **Context awareness**: Copilot uses open files; use `@workspace` for project context
✅ **Chat for complexity**: Use GitHub Copilot Chat for complex questions and discussions
✅ **Reword if stuck**: Try different phrasing or start writing code to autocomplete
✅ **Python-specific**: Works great for FastAPI, Flask, Django, pandas, data science
⚠️ **Vague prompts fail**: Ambiguous prompts like "Create an API endpoint" yield poor results
⚠️ **Specificity wins**: Include framework, method, data format, and requirements in prompts

📚 [What is GitHub Copilot](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/2-what-is-github-copilot) | [Use Copilot with Python](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/4-use-copilot-with-python)
