# TrendTrack-Clothing-Sales-Analysis
This project simulates a complete backend for an online clothing store using MySQL. It models key entities such as Customers, Sellers, Products, Carts, Payments, and Shipping. The system supports:
1.Managing customer and seller information
2.Tracking product inventory by seller
3.Adding products to carts and managing purchases
4.Recording payments and generating purchase history
5.Tracking shipments between customers and sellers
6.Generating insights like top-selling products, monthly sales trends, and customer purchase reports

# Entities with Attributes
Seller
Attributes: Seller_id (PK), Name, Address, Phone_number, S_password
Customer
Attributes: Customer_id (PK), Name, Phone_number, C_password, Street, Pincode
Cart
Attributes: Cart_id (PK), Customer_id (FK)
Product
Attributes: Product_id (PK), Type, Size, Gender, Age_group, Reviews, Cost, Quantity, Seller_id (FK)
Cart_item
Attributes: Cart_id (PK, FK), Product_id (PK, FK), Quantity, Date_added, Purchased, Total_cost
Payment
Attributes: Payment_id (PK), Amount, Payment_date, Customer_id (FK)
Shipping
Attributes: Tracking_id (PK), Customer_id (FK), Seller_id (FK)

# Relationships
Customer ― Cart	1-to-1	One customer has one cart
Cart ― Cart_item ― Product	Many-to-Many	A cart can have many products, and a product can be in many carts
Cart_item ― Product	Many-to-1	Each cart item refers to one product
Product ― Seller	Many-to-1	Many products can belong to one seller
Customer ― Payment	1-to-Many	One customer can make many payments
Customer ― Shipping ― Seller	Many-to-Many	Multiple shipping records between customers and sellers
Customer ― Cart_item (via Cart)	1-to-Many	One customer can have multiple cart items


