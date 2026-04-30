# Design Pattern Implementation (Strategy Pattern)

**Prompt Used**
Analyze the following JavaScript code and identify opportunities to apply the Strategy Pattern.

Refactor the code to remove complex conditional logic by introducing separate strategy classes or functions.

Ensure the refactored code:
-Maintains the same functionality
-Improves readability and maintainability
-Makes it easy to add new shipping methods

Explain the changes made and why the Strategy Pattern is appropriate.

**Response (Summary)**

The AI identified that:

The function has too many nested if/else statements
Shipping logic is tightly coupled
Hard to extend (e.g. adding a new shipping method)

Suggested solution:
Use the Strategy Pattern by:

Creating separate strategies for each shipping method
Delegating logic instead of using conditionals



**Refactored Code (Strategy Pattern)**

// Strategy implementations
const standardShipping = (pkg, country) => {
  let cost;

  if (country === 'USA') cost = pkg.weight * 2.5;
  else if (country === 'Canada') cost = pkg.weight * 3.5;
  else if (country === 'Mexico') cost = pkg.weight * 4.0;
  else cost = pkg.weight * 4.5;

  if (pkg.weight < 2 && (pkg.length * pkg.width * pkg.height) > 1000) {
    cost += 5.0;
  }

  return cost;
};

const expressShipping = (pkg, country) => {
  let cost;

  if (country === 'USA') cost = pkg.weight * 4.5;
  else if (country === 'Canada') cost = pkg.weight * 5.5;
  else if (country === 'Mexico') cost = pkg.weight * 6.0;
  else cost = pkg.weight * 7.5;

  if ((pkg.length * pkg.width * pkg.height) > 5000) {
    cost += 15.0;
  }

return cost;
};

const overnightShipping = (pkg, country) => {
  if (country === 'USA') return pkg.weight * 9.5;
  if (country === 'Canada') return pkg.weight * 12.5;

  throw new Error("Overnight shipping not available for this destination");
};

// Strategy selector
const shippingStrategies = {
  standard: standardShipping,
  express: expressShipping,
  overnight: overnightShipping
};

// Main function
function calculateShippingCost(packageDetails, destinationCountry, shippingMethod) {
  const strategy = shippingStrategies[shippingMethod];

  if (!strategy) {
    throw new Error("Invalid shipping method");
  }

  const cost = strategy(packageDetails, destinationCountry);
  return cost.toFixed(2);
}

**What Changed**

Before:

One big function
Multiple nested if/else
Hard to read and maintain

After:

Each shipping method is its own function (strategy)
Main function just selects and runs a strategy
Code is clean, modular, and scalable

**Benefits of Strategy Pattern**
-Easier to read
-Easier to maintain
-Easy to add new shipping methods (just add a new function)
-Removes complex conditionals

**Reflection**

How did implementing the pattern improve maintainability?

It separated shipping logic into independent strategies, making the code easier to update and manage.

What future changes will be easier?

Adding new shipping methods or modifying existing ones without touching the main function.

Any challenges?

Understanding how to split logic into strategies and organize them properly.