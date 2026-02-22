# Learning Guide - unknown

> **Welcome to Product-Track Week 9, Hotfix 1!**
> This is a **hotfix task** - a single file that needs urgent bug fixes.
> Hotfixes simulate real production emergencies where you need to fix code quickly.

---

## What You Need To Do (Summary)

1. **Read the comments** at the top of `gitignore_fix.txt` - they describe the problem
2. **Read** this guide to learn the unknown syntax you'll need
3. **Find the bugs** (search for `BUG` comments in the code)
4. **Fix each bug** using the hints provided
5. **Run the tests** (if included at the bottom of the file)

---

## JavaScript (Node.js) Quick Reference

### Variables and Types
```javascript
const name = "Alice";           // constant - can't be reassigned
let count = 42;                 // variable - can be reassigned
const items = [1, 2, 3];       // array
const config = {key: "value"};  // object
const isActive = true;          // boolean
// DON'T use 'var' - it has scoping issues
```

### Functions
```javascript
// Regular function
function greet(name, greeting = "Hello") {
    return ${greeting}, !;    // Template literal (backticks)
}

// Arrow function (shorter syntax, same thing)
const greet = (name) => Hello, !;

// Calling:
const result = greet("Alice");
```

### Classes
```javascript
class Calculator {
    constructor() {                     // Constructor
        this.history = [];              // 'this' = current object
    }

    add(a, b) {                         // Method
        const result = a + b;
        this.history.push(result);
        return result;
    }

    getHistory() {
        return [...this.history];       // Return a copy
    }
}

// Using it:
const calc = new Calculator();
calc.add(2, 3);
console.log(calc.getHistory());        // [5]

// Exporting (so other files can use it):
module.exports = Calculator;

// Importing:
const Calculator = require('./Calculator');
```

### Objects (Key-Value Storage)
```javascript
const user = {name: "Alice", age: 25};
user.name;                              // Access: "Alice"
user["name"];                           // Also works
user.email = "alice@test.com";          // Add/update
"name" in user;                         // Check key exists: true
const {name, age} = user;              // Destructuring
```

### Arrays
```javascript
const items = [1, 2, 3];
items.push(4);                          // Add to end
items.pop();                            // Remove last
items.length;                           // Length: 3
items.map(x => x * 2);                 // Transform: [2, 4, 6]
items.filter(x => x > 1);             // Filter: [2, 3]
items.forEach(item => console.log(item));  // Loop
```

### Error Handling
```javascript
try {
    const result = riskyOperation();
} catch (error) {
    console.error(Error: );
} finally {
    cleanup();
}
```

### Common Patterns You'll See
```javascript
// Null/undefined checks
if (!value) { return "Empty"; }             // falsy check
if (value === null) { return "Null"; }      // strict null check
if (value === undefined) { return "Undef"; } // strict undefined

// == vs === (IMPORTANT!)
"5" == 5      // true  (loose - converts types)
"5" === 5     // false (strict - checks type too)
// ALWAYS use === in real code

// Ternary operator
const status = isActive ? "active" : "inactive";

// Optional chaining
const city = user?.address?.city;  // undefined if any part is null
```

### How to Run Tests
```bash
# From the task folder:
npx jest tests/ --verbose

# Or if Jest is installed:
npm test
```

### How to Add a Test
```javascript
// In the test file:
test('should do something specific', () => {
    const obj = new MyClass();
    const result = obj.method(inputData);
    expect(result).not.toBeNull();        // Not null
    expect(result).toBe(expectedValue);   // Exact match
    expect(result.length).toBeGreaterThan(0);  // Comparison
});
```

---

## Project Structure

This is a **hotfix** - everything is in one file:

| File | Purpose |
|------|---------|
| `gitignore_fix.txt` | The code with bugs - **fix this file** |
| `GUIDE.md` | This learning guide |

---

## Incident Reports

### Bug #1
**User Report / Alert:**
> "The current .gitignore is nearly empty — most patterns are missing."

**Error Log Snippet:**
```
[ERROR] Exception in module -- Unexpected behavior detected.
```

**Approach hint:** The stack trace and user report suggest an issue in this file. Investigate the execution flow to identify the root cause.



### Bug #2
**User Report / Alert:**
> "node_modules pattern is commented out! Uncomment it."

**Error Log Snippet:**
```
[ERROR] Exception in module -- Unexpected behavior detected.
```

**Approach hint:** The stack trace and user report suggest an issue in this file. Investigate the execution flow to identify the root cause.



### Bug #3
**User Report / Alert:**
> "No .env pattern! Secrets are being tracked!"

**Error Log Snippet:**
```
[ERROR] Exception in module -- Unexpected behavior detected.
```

**Approach hint:** The stack trace and user report suggest an issue in this file. Investigate the execution flow to identify the root cause.



### Bug #4
**User Report / Alert:**
> "No __pycache__ pattern!"

**Error Log Snippet:**
```
[ERROR] Exception in module -- Unexpected behavior detected.
```

**Approach hint:** The stack trace and user report suggest an issue in this file. Investigate the execution flow to identify the root cause.



### Bug #5
**User Report / Alert:**
> "No IDE patterns (.vscode/, .idea/)"

**Error Log Snippet:**
```
[ERROR] Exception in module -- Unexpected behavior detected.
```

**Approach hint:** The stack trace and user report suggest an issue in this file. Investigate the execution flow to identify the root cause.



### Bug #6
**User Report / Alert:**
> "No OS file patterns (.DS_Store, Thumbs.db)"

**Error Log Snippet:**
```
[ERROR] Exception in module -- Unexpected behavior detected.
```

**Approach hint:** The stack trace and user report suggest an issue in this file. Investigate the execution flow to identify the root cause.



### Bug #7
**User Report / Alert:**
> "No pattern for *.key, *.pem, secrets/"

**Error Log Snippet:**
```
[ERROR] Exception in module -- Unexpected behavior detected.
```

**Approach hint:** The stack trace and user report suggest an issue in this file. Investigate the execution flow to identify the root cause.



---

## How to Approach This

1. **Read the top comment block** in `gitignore_fix.txt` carefully - it has:
   - The JIRA ticket description (what's happening in production)
   - Slack thread (discussion about the problem)
   - Acceptance criteria (checklist of what needs to work)
2. **Search for `BUG`** in the file to find each bug location
3. **Read the surrounding code** to understand what it's trying to do
4. **Fix the logic** based on the bug description
5. **Check the tests** at the bottom of the file and make sure they pass

---

## Common Mistakes to Avoid

- Don't change the structure of the code - only fix the buggy logic
- Read **all** the bugs before starting - sometimes fixing one helps you understand another
- Pay attention to the Slack thread comments - they often contain hints about the root cause
