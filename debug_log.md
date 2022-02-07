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

```
TypeError: 'topping' is an invalid keyword argument for PizzaTopping
```

I found when new order was made the program wasn't showing the pizza order even though it should've. So, I used the trace backward technique by searching the invaild keyword `topping` in the code. I discovered the bug on line 87 file in `app.py` it was caused by an incorrect property name `topping` instead of `topping_type` while creating a object of `PizzaTopping`. Fixed!

```
werkzeug.routing.BuildError: Could not build url for endpoint '/'. Did you mean 'fulfill_order' instead?
```

Then I noticed another bug on line 93 in app.py the redirect path returned the error-message above. The bug was caused by using `/` instead of `home`. Changed `redirect(url_for('/'))` to `redirect(url_for('home'))`. Fixed!

```
sqlalchemy.exc.IntegrityError: (sqlite3.IntegrityError) NOT NULL constraint failed: pizza.order_name
[SQL: INSERT INTO pizza (order_name, size, crust_type, fulfilled) VALUES (?, ?, ?, ?)]
[parameters: (None, None, 'THICK', 0)]
```

New error when attempting to insert a `Pizza` object. In the function `pizza_order_submit` the variable `order_name` on line 76 is `None`. The form input name in `order.html` isn't matching. Changed `order_name = request.form.get('name')` to `order_name = request.form.get('order_name')`. Fixed!

Same problem with `pizza_size_str` on line 77. Changed `pizza_size_str = request.form.get('size')` to `pizza_size_str = request.form.get('pizza_size')`. Fixed!

I noticed that the `toppings` for the pizza object was returning the wrong value. Changed line 79 `toppings_list = request.form.get('toppings')` to  `toppings_list = request.form.getlist('toppings')`.
Line 86 `for topping_str in ToppingType:` to `for topping_str in toppings_list:`. Fixed!

The last and final bug I found was that the pizza data wasn't commited after being added to the session. Included `db.session.commit()` after `db.session.add(pizza)`. Fixed!

## Exercise 2

[[Your answer goes here!]]

## Exercise 3

[[Your answer goes here!]]
