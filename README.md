
# Python Object Oriented Cash Register Lab

## Introduction
In this lab we will be mimicing the functionality of a cash register with our knowledge of object oriented Python. Our cash register will be able to add items of different quantities and prices to our cart, calculate discounts, keep track of what items have been added, and void transactions.

## Objectives

* Build a class with instance methods
* Call instance methods inside of other instance methods
* Use instance methods to track information pertinent to an instance of a class

## Instructions

We will need to build a CashRegister class that creates a cash register with a total (`_total`) which starts at `0`, an empty list of items (`_items`), and an optional employee discount (`_employee_discount`).

Next define instance methods that use decorators for these attributes to both read and write (get and set) these attributes, which should be named `total`, `items`, and `employee_discount`.

> **note:** remember to load the autoreload extension from IPython
```python
%load_ext autoreload
%autoreload 2
```


```python
from cash_register import CashRegister
```


```python
cash_register = CashRegister()
```


```python
print(cash_register.total)
print(cash_register.employee_discount)
```

Next, we want to define an instance method called `add_item` that will add an item to our cart. It should take in the name of an item, its price and an optional quantity. The method should increase the cash registers total by the appropriate amount and return the new total for the cash register.

> **hint:** think about how you would like to keep this information in your list of items. Can we imagine wanting to ever check the price of an individual item after we've added it to our cart? What data type do we know of that can associate the item name with it's price?


```python
cash_register.add_item("rainbow sandals", 45.99) # 45.99
```


```python
cash_register.add_item("agyle socks", 10.50) # 56.49
```


```python
cash_register.add_item("jeans", 50.00, 3) # 206.49
```

We have been spending a lot the past few weeks and are getting a lot of buyers remorse. Let's see if we can play around with the math to justify our purchases to ourselves. Let's define two instance methods: `average_item_price` and `median_item_price`, which should return the average price per item and the median price of the items in your cart, respectively. 


```python
cash_register.average_item_price()
```


```python
cash_register.median_item_price()
```

## More TALKING HERE

Now, define an instance method called `apply_discount` that applies a discount if one is provided and returns the discounted total. For example, if we initialize a new cash register with a discount of 20% then our total should be discounted in the amount of 20%. So, if our total were `$100`, after the discount we would only owe `$80`.

If our cash register does not have an employee discount, then it should return a string saying: `"Sorry, there is no discount to apply to your cart :("`


```python
discount_cash_register = CashRegister(20)
print(discount_cash_register.add_item("rainbow sandals", 45.00)) # 45.00
print(discount_cash_register.add_item("agyle socks", 15.00)) # 60.00
print(discount_cash_register.apply_discout()) # 48.00
print(discount_cash_register.add_item("macbook air", 1000.00)) # 1060.00
print(discount_cash_register.apply_discout()) # 848.00
print(cash_register.apply_discount())
```

Great, we have a way to add items, view our total, and apply discounts. We now want to be able to view a list of all items in our cart. Let's define an instance method called `items` which returns a list of names which represent each item we have in our cart -- if there are three socks the list should contain three `"socks"`. 


```python
cash_register.items() 
# ["rainbow sandals", "argyle socks", "jeans", "jeans", "jeans"]
```

Finally, we are missing one piece of functionality. What if we added something to our cart that we would like to remove? Let's define a method that, given a name, removes the first item from our cart with that name, updates the cash registers total, and finally returns the new total.

## Summary
In this lab, we practiced using instance methods to mimic the functionality of a shopping cart. 
