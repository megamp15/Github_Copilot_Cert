# Prompt Engineering Cheat Sheet

## The 4 Ss (Golden Rules)

1. **Single** - One task per prompt
2. **Specific** - Be explicit and detailed
3. **Short** - Concise but complete
4. **Surround** - Provide context (open related files)

## Quick Prompt Templates

### Zero-Shot (No Examples)
```
# Calculate the factorial of a number
```

### One-Shot (Single Example)
```
# Convert temperature from Celsius to Fahrenheit
def celsius_to_fahrenheit(celsius):
    return (celsius * 9/5) + 32

# Convert temperature from Fahrenheit to Celsius
```

### Few-Shot (Multiple Examples)
```
# Morning greeting
if hour < 12:
    return "Good morning"

# Afternoon greeting
elif hour < 18:
    return "Good afternoon"

# Evening greeting
```

## Role Prompting Templates

### Security Focus
```
Act as a cybersecurity expert. Create a password validation function
following OWASP guidelines with:
- Minimum length check
- Complexity requirements
- Common password detection
```

### Performance Focus
```
Act as a performance optimization expert. Refactor this function
to handle large datasets (1M+ records) efficiently.
```

### Testing Focus
```
Act as a testing specialist. Create comprehensive unit tests including:
- Happy path scenarios
- Edge cases
- Error conditions
- Boundary values
```

## Context Management

### File-Specific
```
#file:controller.js explain the authentication logic
```

### Workspace-Wide
```
@workspace where is the database connection configured?
```

### Terminal-Specific
```
@terminal how do I find all .log files larger than 100MB?
```

## Iteration Strategy

❌ **Don't**: Accept first suggestion if not perfect

✅ **Do**:
1. Review suggestion
2. Erase code
3. Add more details to comment
4. Try again
5. Repeat until satisfied

## PRU-Efficient Prompting

### Save PRUs (1 PRU each)
- Use specific, clear prompts first time
- Break complex tasks into smaller prompts
- Use inline suggestions when possible
- Standard model for routine tasks

### Worth Extra PRUs (2+ PRUs)
- Complex architectural decisions
- Security-critical code review
- Advanced algorithm design
- Full project generation (@workspace /new)

## Common Patterns

### Generate Function
```
// Function to <action> <object>
// Input: <parameter description>
// Output: <return value description>
// Edge cases: <list edge cases>
```

### Refactor Code
```
// Refactor this to:
// 1. Use modern ES6 syntax
// 2. Improve error handling
// 3. Add input validation
<existing code>
```

### Fix Bug
Select code → `Ctrl+I` → `/fix`
or
```
// This code has a bug where <describe bug>
// Expected behavior: <describe expected>
// Current behavior: <describe actual>
<buggy code>
```

### Generate Tests
```
/tests using Jest for the following function:
<function code>

Include tests for:
- Valid inputs
- Invalid inputs
- Edge cases
- Error handling
```
