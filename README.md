# Flask-application-for-online-food-delivery

This is a complete backend system for a Restaurant Website, implemented in Flask, which allows you to signup
customers and vendors, login them using their credentials, as a vendor add items in the
database, as a customer place an order, and as an admin I should be able to see all the orders
placed etc.

Program Organization
The simple program is structured in various layers.

1. Models: In this package we have different python files named as Models.py,
Database.py, UserSession.py. All these files are designed to do certain tasks.

    a. Models.py: This file has classes for different tables that will be created inside the
    database. The tables that are being created are:
      i. Customer(cust_id, name, username, password, level), here level → 0 is
        for customer, level → 1 for vendors and level→ 2 for admin.
      ii. Vendor(vendor_id, cust_id, restaruant_name)
      iii. Food(food_id, vendor_id, dish_name, calories_per_gm,
        available_quantity, unit_price)
      iv. Orders(order_id, cust_id, total_amount, date)
      v. OrderItems(item_id, order_id, food_id, quantity, amount)

2. apis.py
This file is designed to call some of the implemented APIs such as adding
customer, login, add_vendor, add_dish, search_by_dish, search_by_restaurant,
place_order, get_all_orders, get_all_vendors and logout.
    a. Add_customer: This is a signup API. This should take, “name, username,
    password, level” as parameters. Here level is 0 for customer, 1 for vendor and 2
    for Admin.
    b. Login: This API should take the username and password of signed up users and
    successfully log them in.
    c. Logout: This API should logout the customer.
    d. Add_vendor: Only added customers can be made vendors. This API should take
    “customer_id, store_name” as parameters.
    e. Get_all_vendors: Only logged in users can call this API. This should return all
    the vendor details with their store and item offerings
    f. Add_item: Only logged in vendors can add items. This API should take, “item_id,
    item_name, vendor_id, store_id, available_quantity, unit_price”
    g. Place_order: Only logged in customers can place orders. This API should take,
    “customer_id, item_id, quantity” as parameters.
    h. Get_all_orders_by_customer: Only logged in users can call this API. This
    returns all the orders placed by that customer. This should take “customer_id” as
    a parameter.
    i. Get_all_orders: Only admin can call this API. This API returns all the orders in
    the orders table.

3. main.py
  a. This is a simple python script to start the application, once the application is
  started we should be able to call the API’s and see the output accordingly.


