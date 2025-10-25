# Unit Testing with GitHub Copilot - Quick Guide

## ⚡ Quick Start (3 Steps)

1. **Setup**: `/setupTests` in Chat → Follow guidance
2. **Generate**: Select code → `/tests` or "Generate Tests" smart action
3. **Fix**: Hover failing test → Click sparkle icon → Apply fix

## 🛠️ Four Ways to Generate Tests

| Method               | When to Use                | How                                           |
| -------------------- | -------------------------- | --------------------------------------------- |
| **Chat view**        | Project/class/method tests | Chat → `/tests` or describe in Ask/Edit mode  |
| **Inline Chat**      | Selected code              | Select → `Ctrl+I` → `/tests`                  |
| **Smart action**     | Fastest way                | Select code → Right-click → "Generate Tests"  |
| **Code completions** | Add more tests             | Start typing in test file, accept suggestions |

## 📝 Testing Slash Commands

| Command           | Purpose                              |
| ----------------- | ------------------------------------ |
| `/setupTests`     | Configure test framework for project |
| `/tests`          | Generate unit tests for code         |
| `/fixTestFailure` | Fix failing tests                    |

## 🔧 C# Test Framework Setup

### Quick Setup (Command Palette: `Ctrl+Shift+P` / `Cmd+Shift+P`)

**xUnit**:

```bash
.NET:New Project... → xUnit Test Project
dotnet add [test.csproj] reference [project.csproj]
```

**NUnit**:

```bash
.NET:New Project... → NUnit3 Test Project
dotnet add [test.csproj] reference [project.csproj]
```

**MSTest**:

```bash
.NET:New Project... → MSTest Test Project
dotnet add [test.csproj] reference [project.csproj]
```

### Requirements (C#)

- .NET 8.0+ SDK
- C# Dev Kit extension
- Test framework package (xUnit/NUnit/MSTest)

## 🎯 Test Explorer Features

| Feature                | How to Access                           |
| ---------------------- | --------------------------------------- |
| **Open Test Explorer** | Click beaker icon on Activity bar       |
| **Run test**           | Click green play button next to test    |
| **Debug test**         | Right-click test → Debug                |
| **View results**       | Test Explorer updates automatically     |
| **Navigate to code**   | Click stack trace link                  |
| **Run all tests**      | Command Palette → "Test: Run All Tests" |

## 🐛 Fix Failing Tests (2 Methods)

**Method 1 - Test Explorer**:

1. Hover over failing test
2. Click sparkle icon (Fix Test Failure)
3. Review & apply

**Method 2 - Chat Command**:

- Chat → `/fixTestFailure` → Follow suggestions

**💡 Agent Mode**: Auto-fixes and reruns failing tests

## ✍️ Prompt Examples

**Generate comprehensive tests**:

```
Write unit tests for the #selection including:
- Happy path scenarios
- Edge cases
- Error handling
- Boundary conditions
```

**For single method**:

```
Write a unit test for the method in the #editor
```

**For specific framework**:

```
Generate xUnit tests for this class with test data attributes
```

## 🎨 Customize Test Generation

Provide custom instructions for:

- Preferred frameworks
- Naming conventions
- Code structure
- Test patterns/methodologies

## ⚠️ Remember

✅ Copilot generates comprehensive tests
✅ Recognizes your test framework & style
✅ Suggests edge cases you might miss

❌ Generated tests may not cover everything
❌ Always review and add manual tests
❌ Code review is still necessary
