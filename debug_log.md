# Debug Log

**Explain how you used the the techniques covered (Trace Forward, Trace Backward, Divide & Conquer) to uncover the bugs in each exercise. Be specific!**

In your explanations, you may want to answer:

- What is the expected vs. actual output?
- If there is a stack trace, what useful information does it contain?
- Which technique did you use, on which line numbers?
- What assumptions did you have about each line of code, and which ones were proven to be wrong?

_Example: I noticed that the program should show pizza orders once a new order is made, and that it wasn't showing any. So, I used the trace forward technique starting on line 13. I discovered the bug on line 27 was caused by a typo of 'pzza' instead of 'pizza'._

_Then I noticed another bug ..._

## Exercise 1

After running the website on my local machine I went through the user flow. I found that once the new order was made the program wasn't showing the pizza order even though it should've. So, I used the trace backward technique by searching the invaild keyword in the code. I discovered the bug on line 79 file in app.py it was caused by an incorrect variable name 'topping' instead of 'topping_type' while creating a object of PizzaTopping.

## Exercise 2

[[Your answer goes here!]]

## Exercise 3

[[Your answer goes here!]]
