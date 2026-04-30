Performance Optimization Challenge

Selected Scenario:
Slow Code Analysis (Python)

**Prompt used**
I have a piece of Python code that is running very slowly and I want to understand why. I am still learning programming, so please explain things in a simple way.

Here is the code:

def find_product_combinations(products, target_price, price_margin=10):
results = []

for i in range(len(products)):
for j in range(len(products)):
if i != j:
product1 = products[i]
product2 = products[j]

combined_price = product1['price'] + product2['price']

if (target_price - price_margin) <= combined_price <= (target_price + price_margin):
if not any(r['product1']['id'] == product2['id'] and
r['product2']['id'] == product1['id'] for r in results):

pair = {
'product1': product1,
'product2': product2,
'combined_price': combined_price,
'price_difference': abs(target_price - combined_price)
}
results.append(pair)

results.sort(key=lambda x: x['price
   
  
**Prompt Response**

**Problem Overview**

The function is used to find pairs of products where their combined price is close to a target price.

It processes a large list of products (around 5,000 items)
Current execution time is around 20–30 seconds
This causes slow loading in the application

**Error / Performance Description**

The code runs slowly because it compares every product with every other product.

This means:

A lot of repeated comparisons are happening
The program does more work than necessary
Performance becomes worse as the number of products increases

**Root Cause (Performance Bottlenecks)**

The main issues are:

Nested loops
The code uses a loop inside another loop, which makes it run many times
Duplicate comparisons
It checks both:
Product A with Product B
Product B with Product A
(which is unnecessary)
Extra duplicate check using any()
This adds more processing inside the loop, making it slower

**Suggested Solution / Optimization**

To improve performance:

Only compare each pair once
Avoid duplicate checks by fixing the loop logic
Reduce unnecessary operations inside loops

 Improved Loop Example:
for i in range(len(products)):
    for j in range(i + 1, len(products)):
        product1 = products[i]
        product2 = products[j]

This change:

Removes duplicate comparisons
Reduces the number of loop iterations
Makes the code more efficient


**Performance Improvement**

Before: ~20–30 seconds
After: Faster execution due to fewer comparisons

Even though exact timing was not measured, the improvement is significant because the number of operations is reduced.

**Learning Points**

Nested loops can slow down a program a lot
Avoid repeating the same work in loops
Always think about efficiency when working with large data
Small changes in logic can improve performance a lot

**Reflection**

How did the optimization change your understanding?

It helped me understand that how loops are written has a big impact on performance, especially with large datasets.

Were the improvements significant?

Yes, because reducing duplicate comparisons makes the program run faster and more efficiently.

What did you learn about performance?

I learned that nested loops can be expensive and that it is important to avoid unnecessary operations inside loops.

How would you approach similar issues in the future?

I would try to think about efficiency when writing code and avoid repeating the same work.

What tools or techniques would you use?

I can use tools like time.time() to measure execution time and compare performance before and after changes.

**Conclusion**

The main issue was inefficient looping and duplicate work.
By improving how the loops are structured, the performance can be significantly improved.


