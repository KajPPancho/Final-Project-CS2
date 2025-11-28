# Ecommerce, FINAL PROJECT FOR CS 2
# Project Statement
This project will let us solve the large variations in order values that reflects the important differences in consumer purchasing manner, economic capability and as well as types of products. This problem is very important and worth solving because there is this sub problem, that is now very common in the Philippine economic system whiich should be prevented or avoided, this is corruption. Large variation in order values relates to our JSON file, ecommerce.json because it focuses on the amount of money or in short economics that may have large variation to one of the order values.
# Project Objectives
This project allows the user to:
1. Analyze the large variation in order values in the ecommerce.json file
2. Determine if such values lead to higher amounts or may lead to equality
3. Apply it in real life situation involving economics such as ecommerce
# Planned Features
1. Feature 1: Calculate the total revenue of an order.
2. Feature 2: Find the most expensive item in the order.
3. Feature 3: Find the cheapest item in the order.
4. Feature 4: Show the total amount spent by costumer.
5. Feature 5: Calculate which product was ordered the most based on quantity.
# Planned Inputs and Outputs
1. Input 1: order_id
2. Input 2: customer
3. Input 3: order_date
4. Input 4: payment_method
5. Input 5: shipping_address
6. Input 6: product
7. Input 7: category
8. Input 8: price
9. Input 9: quantity

   Outputs:
  - Most sold product
  - Least sold product
  - Average amount of products ordered per table
  - Average spend per customer
  - Amount of customers served in a specific time frame

# Logic Plan

(Pseudocode)

START

// Define lists or groups for the inputs.
DEFINE Order:
    order_id
    customer
    order_date
    payment_method
    shipping_address
    product
    category
    price
    quantity

// Create a list to store all orders.
DECLARE orders_list as LIST OF Order

// Then, the inputs
WHILE more orders exist:
    READ order_id
    READ customer
    READ order_date
    READ payment_method
    READ shipping_address
    READ product
    READ category
    READ price
    READ quantity
    CREATE order_object with above inputs
    APPEND order_object to orders_list

// Feature 4
DECLARE customer_totals as DICTIONARY
FOR each order IN orders_list:
    IF customer_totals[order.customer] EXISTS:
        customer_totals[order.customer] += order.total_revenue
    ELSE:
        customer_totals[order.customer] = order.total_revenue

// Feature 5
DECLARE product_quantities as DICTIONARY
FOR each order IN orders_list:
    IF product_quantities[order.product] EXISTS:
        product_quantities[order.product] += order.quantity
    ELSE:
        product_quantities[order.product] = order.quantity

most_sold_product = product WITH MAX value in product_quantities
least_sold_product = product WITH MIN value in product_quantities
