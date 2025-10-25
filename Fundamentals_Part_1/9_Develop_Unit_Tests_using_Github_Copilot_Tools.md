# Examine the unit testing tools and environment

## GitHub Copilot for Unit Testing Overview

**What Copilot does**:

- Suggests unit tests based on method signatures and code context
- Generates test cases covering input parameters and expected outputs
- Provides code completion suggestions for additional test cases
- Suggests assertions for edge cases and boundary conditions (error handling, null values, unexpected types)

⚠️ **Important**: Generated tests may not cover all scenarios. Manual testing and code reviews are still necessary.

## GitHub Copilot Testing Capabilities

| Task                          | What Copilot Does                                                    |
| ----------------------------- | -------------------------------------------------------------------- |
| **Set up testing frameworks** | Configure frameworks & VS Code extensions for your project/language  |
| **Generate test code**        | Create unit tests, integration tests, end-to-end tests               |
| **Handle edge cases**         | Generate comprehensive test suites for edge cases & error conditions |
| **Fix failing tests**         | Provide suggestions for fixing test failures                         |
| **Maintain consistency**      | Generate tests following your project's coding practices             |

### Setup Testing Framework

**Quick setup** using `/setupTests` command:

1. Open Chat view
2. Enter `/setupTests` in chat input
3. Follow Copilot's guidance to configure

### Write Unit Tests - Four Methods

| Method                    | Use Case                                | How to Use                                           |
| ------------------------- | --------------------------------------- | ---------------------------------------------------- |
| **Chat view**             | Generate tests for project/class/method | Use Ask, Edit, or Agent mode                         |
| **Inline Chat**           | Generate tests for selected code        | Select classes/methods, use Inline Chat              |
| **Smart actions**         | Quick test generation                   | Use "Generate Tests" smart action (no prompt needed) |
| **Code line completions** | Add more tests to existing suite        | Auto-suggest additional test cases                   |

**Prompt examples**:

- Single method visible: `Write a unit test for the method in the #editor`
- Multiple methods/long code: Select code → `#selection write a unit test for this code`

### Fix Failing Tests

**Method 1 - Test Explorer**:

1. Hover over failing test in Test Explorer
2. Select **Fix Test Failure** button (sparkle icon)
3. Review and apply suggested fix

**Method 2 - Chat Command**:

1. Open Chat view
2. Enter `/fixTestFailure` slash command
3. Follow suggestions

💡 **Tip**: Agent mode monitors test output and automatically attempts to fix and rerun failing tests.

### Maintain Consistency

**Customize test generation** with custom instructions:

- Specify preferred testing frameworks
- Define naming conventions
- Set code structure preferences
- Request specific test patterns/methodologies

## Visual Studio Code Unit Testing Setup

### Requirements (for C#)

| Requirement           | Details                         |
| --------------------- | ------------------------------- |
| **.NET SDK**          | .NET 8.0 or later               |
| **VS Code Extension** | C# Dev Kit extension            |
| **Test Framework**    | xUnit, NUnit, or MSTest package |

### C# Dev Kit Features

| Feature              | Purpose                                                                   |
| -------------------- | ------------------------------------------------------------------------- |
| **Test Explorer**    | Tree view showing all test cases in workspace                             |
| **Run/Debug**        | Run and debug test cases                                                  |
| **Test Results**     | View test results with stack traces                                       |
| **Testing Commands** | Run all tests, run failed tests, etc. (search "Test:" in Command Palette) |
| **Testing Settings** | Configure testing behavior (search "Testing" in Settings)                 |

**Supported frameworks**: xUnit, NUnit, MSTest

### Enable Test Framework

Use Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) to create test projects:

- **xUnit**: `.NET:New Project...` → `xUnit Test Project`
- **NUnit**: `.NET:New Project...` → `NUnit3 Test Project`
- **MSTest**: `.NET:New Project...` → `MSTest Test Project`

Then link to your project: `dotnet add [test.csproj] reference [project.csproj]`

📋 **See**: [Testing Quick Guide](../Quick_Reference/testing-quick-guide.md) for detailed setup commands

## Unit Testing Process (3 Stages)

| Stage                      | Tool                 | Actions                                                                                                                                                   |
| -------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Create Test Project** | VS Code              | • Use Command Palette to create test project with framework<br>• Use Terminal to add reference to target project                                          |
| **2. Generate Test Cases** | GitHub Copilot Chat  | • Write test cases matching your framework & style<br>• Identify edge cases & boundary conditions<br>• Suggest assertions for correctness                 |
| **3. Run & Manage Tests**  | VS Code + C# Dev Kit | • Run/debug with green play button or Test Explorer<br>• View results in editor decorations & Test Explorer<br>• Navigate to source via stack trace links |

## VS Code Testing Features

**Run/Debug**:

- Green play button next to class/method definitions
- Right-click for more options

**Test Explorer**:

- Click beaker button on Activity bar
- View all test cases in tree view
- Run/debug tests from explorer

**Test Results**:

- Updated in editor decorations & Test Explorer
- Click stack trace links to navigate to source

**Commands & Settings**:

- Commands: Search "Test:" in Command Palette
- Settings: Search "Testing" in Settings editor

## Key Takeaways

✅ **Copilot benefits**:

- Context-aware test generation (parameters, outputs, edge cases)
- Reduces repetitive testing work
- Suggests assertions based on code semantics
- Recognizes your test framework and coding style

⚠️ **Remember**: Always combine with manual testing and code reviews for comprehensive quality assurance

📋 [Testing Quick Reference](../Quick_Reference/testing-quick-guide.md) | 📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/develop-unit-tests-using-github-copilot-tools/2-examine-github-copilot-support-unit-tests)

# Create unit tests using the Generate Tests smart action

## What is Generate Tests Smart Action?

A no-prompt-required feature that analyzes code structure and behavior to automatically generate unit tests including assertions and test cases for various scenarios.

**Key benefit**: Fastest way to create tests - no need to write prompts or use chat.

## Two Ways to Use

### 1. Generate Tests for Entire File

**When to use**: Create tests for all functions/methods at once

**Steps**:

1. Open file with code to test
2. Right-click in editor → **Copilot** → **Generate Tests**
3. Copilot analyzes code → generates tests for all functions/methods
4. Tests appear in new test file or at end of current file (depends on project structure)
5. Review generated tests (assertions, test cases, scenarios)
6. **Accept** or **Close** to accept/discard
7. Save test file (typically to `tests/` directory)
8. Run tests to verify functionality
9. Refine as needed (add/modify test cases)

### 2. Generate Tests for Selection

**When to use**: Create tests for specific function/method only

**Steps**:

1. Open file with code to test
2. **Select** the code block to test
3. Right-click selected code → **Copilot** → **Generate Tests**
4. Copilot analyzes selection → generates tests for that function/method
5. Review and adjust as needed
6. Save file
7. Run tests to verify
8. Refine if necessary

## Workflow Summary

```
Code → Right-click → Generate Tests → Review → Accept → Save → Run → Refine
```

## Best Practices

**Review generated tests for**:

- Test names (meaningful and descriptive?)
- Test cases (cover all scenarios?)
- Assertions (validate correct behavior?)
- Edge cases (included or need to add?)

**Then**:

- Run tests to ensure they pass
- Add additional test cases for uncovered scenarios
- Modify assertions if needed
- Save and commit

## Key Advantage

⚡ **Fastest test generation method** - No prompts required, just right-click and generate!

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/develop-unit-tests-using-github-copilot-tools/3-create-unit-tests-generate-tests-smart-action)

# Create unit tests using Inline Chat

## What is Inline Chat for Testing?

Create unit tests directly in the code editor without switching to Chat view. Provides **more control** than Generate Tests smart action through custom prompts.

**Key benefit**: Balance between speed (in-editor) and control (custom prompts)

## When to Use Inline Chat

| Use Inline Chat When            | Use Smart Action When  | Use Chat View When               |
| ------------------------------- | ---------------------- | -------------------------------- |
| Need specific test requirements | Just want quick tests  | Need complex multi-step guidance |
| Want to specify scenarios       | Speed is priority      | Want to discuss approach first   |
| Need edge case control          | Default tests are fine | Require project-wide context     |

## How to Create Tests with Inline Chat

**Steps**:

1. Open file with code to test
2. **Select** code block to test
3. Press **`Ctrl+I`** (Windows/Linux) or **`Cmd+I`** (Mac)
   - _Alternative_: Menu → Editor Inline Chat
4. Enter prompt with `/tests` command
5. Review suggested tests in editor
6. **Accept** or **Close** to accept/discard
7. Save test file (typically to `tests/` directory)
8. Build project to include test file
9. Run tests to verify functionality
10. Refine using Inline Chat if needed

## Example Prompts

**Basic test generation**:

```
/tests Generate unit tests for this method
```

**Comprehensive testing**:

```
/tests Generate unit tests for this method. Validate both success and failure, and include edge cases.
```

**Specific scenarios**:

```
/tests Create tests for this function covering:
- Valid inputs
- Null/empty inputs
- Boundary conditions
- Error handling
```

**Framework-specific**:

```
/tests Generate xUnit tests with test data attributes for various input scenarios
```

## Features

**Inline Chat automatically**:

- Generates tests in existing test file OR creates new one
- Includes assertions for validation
- Covers success and failure scenarios
- Suggests edge cases

**You can adjust**:

- Test names
- Test cases (add/remove/modify)
- Assertions
- Additional scenarios

## Workflow Summary

```
Select Code → Ctrl+I → /tests + prompt → Review → Accept → Save → Build → Run → Refine
```

## Comparison: Smart Action vs. Inline Chat

| Feature           | Smart Action         | Inline Chat              |
| ----------------- | -------------------- | ------------------------ |
| **Speed**         | ⚡⚡⚡ Fastest       | ⚡⚡ Fast                |
| **Control**       | ❌ None (auto)       | ✅ Full (custom prompts) |
| **Prompts**       | Not needed           | Required                 |
| **Customization** | Limited              | High                     |
| **Best for**      | Quick standard tests | Specific requirements    |

## Key Advantage

🎯 **Best of both worlds** - Stay in editor (no context switch) while maintaining full control over test generation through custom prompts!

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/develop-unit-tests-using-github-copilot-tools/4-create-unit-tests-inline-chat)

# Create unit tests using Chat view modes

## Three Chat Modes for Testing

Chat view offers three modes, each optimized for different testing scenarios:

| Mode      | Optimized For        | Best Use Case                  | Context                                         |
| --------- | -------------------- | ------------------------------ | ----------------------------------------------- |
| **Ask**   | Questions & analysis | Multiple functions/entire file | Use `@workspace`, drag files, add external docs |
| **Edit**  | Multi-file edits     | Creating/updating test files   | Use `#codebase`, drag files (no `@workspace`)   |
| **Agent** | Automated workflows  | End-to-end test automation     | Auto-determines context                         |

⚠️ **Important**: Agent mode may make **multiple premium requests** (PRUs depend on task complexity, steps, and model)

## Ask Mode - Analysis & Questions

**Best for**: Workspace analysis, multiple functions, entire files

### How to Use Ask Mode

**Steps**:

1. Open file with code to test
2. Open Chat view → Start chat in **Ask** mode
3. **Add context**:
   - Drag/drop files from EXPLORER into Chat
   - Use **Add Context** button for external files (markdown, guidelines, etc.)
   - Use `@workspace` for workspace-wide context
4. Enter prompt requesting unit tests
5. Review suggested tests, refine with updated prompts
6. Move tests into test file:
   - Create test file manually → insert tests
   - OR use **Apply in Editor** button
7. Save test file (typically to `tests/` directory)
8. Run tests to verify
9. Refine as needed
10. Save again

### Example Prompt

```
@workspace /explain I need to create unit tests for the code in this file.
The tests should be written in Python and use the unittest framework.
```

**Features**:

- ✅ Supports `@workspace` for project-wide context
- ✅ Can add external files (docs, guidelines)
- ✅ Great for asking questions before implementing
- ✅ Refine results with follow-up prompts

## Edit Mode - Multi-File Creation

**Best for**: Creating/updating test files, multi-file edits

### How to Use Edit Mode

**Steps**:

1. Open file with code to test
2. Open Chat view → Start chat in **Edit** mode
3. **Add context**:
   - Use `#codebase` (note: NO `@workspace` in edit mode)
   - Drag/drop files or folders from EXPLORER
   - Use **Add Context** for external files
4. Enter prompt to create unit tests
5. Review test file created by edit mode
6. Save or discard file
7. Update with new prompts if needed
8. Save test file (typically to `tests/` directory)
9. Run tests to verify
10. Refine as needed

### Example Prompt

```
I need to create unit tests for the code in this file.
The tests should be written in Python and use the unittest framework.
Create a test file in the same directory as the code file.
```

**Features**:

- ✅ Creates/updates files directly
- ✅ Multi-file editing capability
- ✅ Uses `#codebase` for context
- ❌ No `@workspace` participant available

## Agent Mode - Automated Workflows

**Best for**: End-to-end automation, complex multi-step tasks, in-depth project understanding

### How to Use Agent Mode

**Steps**:

1. Open file with code to test
2. Open Chat view → Start chat in **Agent** mode
3. **Context auto-determined** (no manual setup needed)
4. _Optional_: Click **Tools** icon to configure:
   - **Test Explorer** tool (run tests)
   - **Terminal** tool (run commands)
   - **GitHub Copilot** tool (code generation)
5. Enter prompt defining all intended tasks
6. **Monitor progress**:
   - Confirm/reject tool invocations
   - Confirm/reject terminal commands
   - Interrupt if needed (change context/tools)
7. Review files created/updated
8. Keep or discard updates
9. Refine with new prompts if needed

### Example Prompt

```
Ensure that a suitable unit tests project is prepared for the selected code file.
Create a test file in the unit test project that includes unit tests for all
methods in the selected file. Unit tests should be written in C# and use the
xUnit framework. Run the tests to ensure expected results.
```

**Features**:

- ✅ Full automation (scaffold project, create files, run tests, generate reports)
- ✅ Auto-determines context and files to edit
- ✅ Configurable tools (Test Explorer, Terminal, Copilot)
- ✅ Interactive (confirm/reject actions, interrupt as needed)
- ⚠️ Uses multiple PRUs for complex tasks

## Mode Comparison

| Feature           | Ask Mode            | Edit Mode              | Agent Mode             |
| ----------------- | ------------------- | ---------------------- | ---------------------- |
| **Speed**         | ⚡ Moderate         | ⚡⚡ Fast              | 🐌 Slower (multi-step) |
| **Control**       | ✅ High             | ✅ High                | ✅ Interactive         |
| **Context**       | `@workspace`, files | `#codebase`, files     | Auto-determined        |
| **File Creation** | Manual + Apply      | Direct                 | Automated              |
| **Multi-file**    | ❌ No               | ✅ Yes                 | ✅ Yes                 |
| **Automation**    | ❌ No               | Limited                | ✅ Full                |
| **PRU Usage**     | 1 PRU               | 1-2 PRUs               | 2+ PRUs (varies)       |
| **Best for**      | Questions, analysis | Creating/editing files | End-to-end workflows   |

## When to Use Each Mode

### Use Ask Mode When:

- Need to analyze workspace before creating tests
- Want to ask questions about testing approach
- Creating tests for multiple functions/entire file
- Need external context (docs, guidelines)
- Want to refine suggestions with follow-up questions

### Use Edit Mode When:

- Need to create/update test files directly
- Working across multiple files
- Want files created automatically
- Don't need workspace-wide context
- Speed is important

### Use Agent Mode When:

- Need full end-to-end automation
- Want to scaffold test projects
- Need tests run automatically
- Want test reports generated
- Task requires deep project understanding
- PRU usage is acceptable

## Quick Decision Guide

```
Simple test for one method → Smart Action
Need custom requirements → Inline Chat
Have questions first → Ask Mode
Need multi-file edits → Edit Mode
Want full automation → Agent Mode
```

## Key Takeaways

✅ **Ask Mode**: Best for analysis and questions with `@workspace` context
✅ **Edit Mode**: Best for direct file creation/editing across multiple files
✅ **Agent Mode**: Best for automated workflows (higher PRU usage)

⚠️ **Agent Mode PRU Warning**: May consume multiple PRUs depending on complexity, steps, and model

📚 [Full Guide](https://learn.microsoft.com/en-us/training/modules/develop-unit-tests-using-github-copilot-tools/5-create-unit-tests-chat-view-modes)
