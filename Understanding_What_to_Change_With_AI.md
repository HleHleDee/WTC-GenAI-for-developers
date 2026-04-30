Code Readability Improvement (Java)

**Prompt used**

This is Java code. Please improve readability.

Focus on:
- variable names
- method names
- class structure
- readability improvements using standard Java naming conventions

Explain what is unclear and suggest improvements without rewriting everything unless necessary. 



**Prompt Response**

**What the code does**

This system manages users:

creates users
validates input
stores users in memory and database
finds users by username


**Issues**

unclear method names (a, f)
unclear class name (U)
poor variable naming
mixed database + logic code
possible SQL injection risk

**AI Improvements**

UserMgr → UserManager
U → User
a() → addUser()
f() → findUser()
improve structure and separation of logic

**Learning**

Naming and structure are key to readability, not just formatting.



# Function Refactoring (Python)

**Prompt Used**
Please refactor this Python function.

Do NOT just rewrite it.
Instead:
- Identify problems in structure
- Suggest smaller helper functions
- Explain how to split responsibilities
- Keep logic the same but improve readability and maintainability


**What the function does**
processes orders
checks inventory
validates customers
calculates price, tax, shipping
updates inventory
tracks revenue

**Issues**
one large function doing everything
repeated validation logic
hard to maintain or test


**AI Refactoring Suggestions**

Split into:

validate_order()
calculate_price()
calculate_tax()
calculate_shipping()
update_inventory()

**Learning**

Smaller functions = easier debugging and testing.



# Code Duplication Detection (JavaScript)

**Prompt Used**

Analyze this JavaScript code and identify duplication patterns.

Do NOT just rewrite it.
Instead:
- point out repeated logic
- suggest reusable helper functions
- explain how to reduce duplication
- consider readability for junior developers

 **What the code does**

Calculates:

average age, income, score
highest age, income, score

**Issues**

repeated loops for same logic
duplicated calculations
not scalable

**AI Suggestion**

Create reusable helpers:

calculateAverage(field)
calculateHighest(field)

**Learning**

Duplication makes code harder to maintain and extend.


**REFLECTION**

Most useful prompt

Refactoring Python function — it showed real-world structure improvement.

-Key AI insights I missed
security issues (SQL injection)
reusable design patterns
hidden duplication patterns

-AI suggestions I disagreed with some naming suggestions were too advanced for beginner level.

-How I would improve prompts
ask for step-by-step explanation
avoid full rewrites
focus on beginner-friendly feedback

-Safety before using AI changes
run tests first
review manually
refactor in small steps
avoid blind copy-paste


**FINAL SUMMARY**

This exercise helped me learn:

how to improve code readability
how to detect duplication

how to refactor safely
how to use AI as a coding assistant
how to think like a developer, not just a coder