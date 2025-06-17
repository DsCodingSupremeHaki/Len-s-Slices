# 🍕 Pizza Toppings and Prices Analysis

This Python script performs a series of operations on a list of pizza toppings and their corresponding prices. It demonstrates basic list manipulations, sorting, and data retrieval in Python.

---

## How It Works

The script initializes two lists: one for pizza **toppings** and another for their respective **prices**. It then performs several tasks:

* Counts how many pizzas cost a specific price.
* Determines the total number of different pizza types sold.
* Combines toppings and prices into a single, two-dimensional list.
* **Sorts** the pizzas by price.
* Identifies the **cheapest** and **priciest** pizzas.
* Simulates the sale of the priciest pizza by **removing** it from the list.
* **Inserts** a new pizza topping ("peppers") with its price into the sorted list, maintaining the sorted order.
* Extracts the **three cheapest** pizzas from the list.

---

## Getting Started

### Prerequisites

You'll only need **Python 3** installed on your computer to run this script.

### Installation

No special installation is required. Just save the code to a `.py` file.

1.  **Save the code:** Copy the entire code block provided and save it as `pizza_analysis.py` (or any other name ending with `.py`) on your computer.

---

## Usage

1.  **Open your terminal or command prompt.**
2.  **Navigate to the directory** where you saved `pizza_analysis.py`.
    ```bash
    cd path/to/your/project
    ```
3.  **Run the script** using Python:
    ```bash
    python pizza_analysis.py
    ```
4.  The script will print various outputs to your console, showing the results of each list manipulation and analysis step as it executes.

---

## Code

Here's the full code for the Pizza Toppings project:

```python
# Pizza Toppings
toppings = ["pepperoni", "pineapple", "cheese", "sausage", "olives", "anchovies", "mushrooms"]

# Pizza Slice Cost
prices = [2, 6, 1, 3, 2, 7, 2]

# Research on $2 slices
num_two_dollar_slices = prices.count(2)
print("Number of $2 slices:", num_two_dollar_slices)

# Length of list of toppings
number_of_pizzas = len(toppings)
print("We sell", number_of_pizzas, "different kinds of pizza!")

# 2D list of toppings & Prices
pizza_and_prices = [[2, "pepperoni"], [6, "pineapple"], [1, "cheese"], \
                    [3, "sausage"], [2, "olives"], [7, "anchovies"], [2, "mushrooms"]]
print("Initial pizza and prices list:", pizza_and_prices)

# Sorting the different pizzas and prices
pizza_and_prices.sort()
print("Sorted pizza and prices by price:", pizza_and_prices)

cheapest_pizza = pizza_and_prices[0]
print("Cheapest pizza:", cheapest_pizza)

priciest_pizza = pizza_and_prices[-1]
print("Priciest pizza:", priciest_pizza)

# Last slice of the priciest pizza was bought, have to remove it from my list
pizza_and_prices.pop(-1)
print("Pizza list after removing priciest:", pizza_and_prices)

# Added a new topping and price relative to the rest of the sorted data
# Find the correct position for insertion to maintain sort order
new_pizza = [2.5, "peppers"]
inserted = False
for i, pizza in enumerate(pizza_and_prices):
    if pizza[0] > new_pizza[0]:
        pizza_and_prices.insert(i, new_pizza)
        inserted = True
        break
if not inserted: # If new_pizza is the most expensive
    pizza_and_prices.append(new_pizza)
print("Pizza list after adding new pizza:", pizza_and_prices)

# Three different type and cheapest pizzas
three_cheapest = pizza_and_prices[0:3]
print("Three cheapest pizzas:", three_cheapest)
```

---

## Learning Context & Credits

This project was developed as part of the **"Learn Python 3"** (or similar "Lists" or "Data Structures" focused) curriculum on [Codecademy](https://www.codecademy.com/). It served as a practical exercise to reinforce understanding of **Python lists**, including:

* Creating and manipulating lists
* Using list methods like `count()`, `len()`, `sort()`, `pop()`, and `insert()`
* Accessing list elements by index
* Slicing lists

---

## Future Enhancements (Ideas for Improvement)

This project provides a good foundation for list manipulation. Here are some ideas for how you could expand upon it:

* **User Interaction:** Allow users to input their own pizza toppings and prices, or to "order" pizzas.
* **Functions:** Organize the code into functions (e.g., `get_cheapest_pizza()`, `add_new_pizza()`) for better modularity and readability.
* **Error Handling:** Add checks for invalid inputs if user interaction is implemented.
* **Dictionary for Pizzas:** Consider using a dictionary to store pizza names and prices (`{"pepperoni": 2, "pineapple": 6}`), which might be more intuitive for lookup operations.
* **Object-Oriented Approach:** For a more complex system, you could create a `Pizza` class with properties like `name` and `price`.

---
