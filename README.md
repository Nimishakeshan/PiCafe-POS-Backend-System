# PiCafe-POS-Backend-System
Developed 9+ RESTful APIs for authentication, order processing, employee management, and customer feedback using Java, Spring Boot, and MySQL, enabling secure and scalable backend operations for a restaurant POS system.

URL--->http://localhost:8080
1. Login API for Authentication/Authorization
ENDPOINT URL
pos/api/login
HTTP METHOD
POST
REQUEST BODY
{
"employeeId": 69,
"password": "@_4qPtiAP@"
}
● employee (required): User's username for authentication.
● password (required): User's password for authentication.
RESPONSE BODY
{
"employee": {
"employee_id": 69,
"name": "Nirvi Wason",
"position": "Manager",
"store_id": 1
},
"token":
"eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI2OSIsImlhdCI6MTcxOTI5OTQ4NiwiZXhwIjoxNzE5M
zM1NDg2fQ.HeqkZKutR77v2G7aKqU2JT261ozbvTRpXRFJfyisTao"
}
RESPONSE CODES

● 200 OK: Successful authentication and token generation.
● 401 Unauthorized: Invalid credentials provided.
● 500 Internal Server Error: Unexpected server error.

2. API to Get Categories/Get Items from Category and Item Table
ENDPOINT URL
picafepos/api/v1/categories/items
HTTP METHOD
GET
RESPONSE BODY
{
"Starters": [
{
"price": 234.0,
"name": "Sandwich",
"id": 14
}
],
"Snacks": [
{
"price": 208.0,
"name": "Bagel",
"id": 8
},
{
"price": 168.0,
"name": "Burger",
"id": 15
},

{
"price": 146.0,
"name": "Vegetable Curry",
"id": 22
},
{
"price": 440.0,
"name": "Dumplings",
"id": 30
},
{
"price": 401.0,
"name": "Falafel",
"id": 33
},
{
"price": 379.0,
"name": "Spring Rolls",
"id": 37
},
{
"price": 187.0,
"name": "Idli",
"id": 44
},
{
"price": 262.0,
"name": "Pav Bhaji",
"id": 45

},
{
"price": 233.0,
"name": "Samosa",
"id": 46
},
{
"price": 377.0,
"name": "Chaat",
"id": 47
}
],
"Main course": [
{
"price": 154.0,
"name": "French Toast",
"id": 12
},
{
"price": 423.0,
"name": "Salad",
"id": 13
},
{
"price": 435.0,
"name": "Pizza",
"id": 16
},
{

"price": 357.0,
"name": "Pasta",
"id": 17
},
{
"price": 282.0,
"name": "Beef Stew",
"id": 21
},
{
"price": 305.0,
"name": "Burrito",
"id": 32
},
{
"price": 403.0,
"name": "Hummus",
"id": 34
},
{
"price": 255.0,
"name": "Ramen",
"id": 36
},
{
"price": 275.0,
"name": "Kebab",
"id": 39
},

{
"price": 313.0,
"name": "Gyoza",
"id": 40
},
{
"price": 219.0,
"name": "Biryani",
"id": 41
},
{
"price": 412.0,
"name": "Curry",
"id": 42
},
{
"price": 282.0,
"name": "Dosa",
"id": 43
}
],
"Desserts": [
{
"price": 271.0,
"name": "Croissant",
"id": 7
},
{
"price": 195.0,

"name": "Muffin",
"id": 9
},
{
"price": 281.0,
"name": "Pancakes",
"id": 10
},
{
"price": 434.0,
"name": "Waffles",
"id": 11
},
{
"price": 412.0,
"name": "Steak",
"id": 18
},
{
"price": 409.0,
"name": "Chicken Parmesan",
"id": 19
},
{
"price": 235.0,
"name": "Grilled Salmon",
"id": 20
},
{

"price": 414.0,
"name": "Tiramisu",
"id": 23
},
{
"price": 360.0,
"name": "Cheesecake",
"id": 24
},
{
"price": 266.0,
"name": "Apple Pie",
"id": 25
},
{
"price": 185.0,
"name": "Brownies",
"id": 26
},
{
"price": 150.0,
"name": "Cookies",
"id": 27
},
{
"price": 410.0,
"name": "Ice Cream",
"id": 28
},

{
"price": 331.0,
"name": "Tacos",
"id": 31
},
{
"price": 317.0,
"name": "Pad Thai",
"id": 35
},
{
"price": 369.0,
"name": "Chow Mein",
"id": 38
}
],
"Beverages": [
{
"price": 135.0,
"name": "Cappuccino",
"id": 1
},
{
"price": 351.0,
"name": "Latte",
"id": 2
},
{
"price": 181.0,

"name": "Espresso",
"id": 3
},
{
"price": 122.0,
"name": "Hot Chocolate",
"id": 4
},
{
"price": 363.0,
"name": "Iced Tea",
"id": 5
},
{
"price": 306.0,
"name": "Lemonade",
"id": 6
},
{
"price": 203.0,
"name": "Sushi",
"id": 29
}
]
}
● categories (required): List of categories retrieved from the database.
RESPONSE CODES
● 200 OK: Successful retrieval of categories.
● 500 Internal Server Error: Unexpected server error.

3. API for Single Order Submission
ENDPOINT URL
picafepos/api/v1/orders
HTTP METHOD
POST
REQUEST BODY (RAW-IN JSON FORMAT)
{
"items": {
"1": 2,
"3": 1,
"4": 3
},
"price": 120,
"orderMode": "Dine-in",
"name": "Khushi Capital test2",
"id": 16,
"storeId": 2,
"date": "2024-06-28 10:20:59.000"
}
RESPONSE BODY
{
"order_id": 49830,
"message": "Order successfully created"
}
RESPONSE CODES
● 200 OK: Successful order placement.
● 400 Bad Request: Malformed or invalid request format.
● 500 Internal Server Error: Unexpected server error.

4. API to Retrieve Orders
ENDPOINT URL
/picafepos/api/v1/orders?storeId=10
HTTP METHOD
GET
AUTHORIZATION
● Any authenticated user can access this endpoint.
RESPONSE BODY-GET ALL ORDER DETAILS BASED ON THE SYSTEM DATE OF THE STORE
{AS TODAY'S DATE IS:21/06/2024 BUT NO ORDERS IS CREATED SO IT WILL SHOW NULL}
LIKE: RESPONSE:{}
{
"orders": [
{
"order_id": "order_id",
"item_id": "item_id",
"quantity": 10
// Other order details...
},
{
"order_id": "order_id",
"item_id": "item_id",
"quantity": 5
// Other order details...
}
]
}
RESPONSE CODES

● 200 OK: Successfully retrieved list of orders.
● 401 Unauthorized: Unauthorized access (user is not authenticated).
● 500 Internal Server Error: Unexpected server error.
5. API to Send Customer Feedback
ENDPOINT URL
picafepos/api/v1/orders/feedback
HTTP METHOD
POST
REQUEST PARAMETERS
{"orderId": 1,
"ratings":
{
"foodrating": 4,
"customerexprating": 5,
"ambiancerating": 2
}
}
RESPONSE BODY
{
"message": "Feedback submitted successfully",
"order_id": 1,
"ratings": {
"foodrating": 4,
"customerexprating": 5,
"ambiancerating": 2
}
}

● message: A confirmation message indicating successful submission of
feedback.
● order_id: The ID of the order for which feedback was submitted.
● ratings: Echo of the ratings submitted by the customer.
RESPONSE CODES
● 200 OK: Order deleted successfully.
● 401 Unauthorized: Unauthorized access (user is not authorized).
● 404 Not Found: Order with specified ID not found.
● 500 Internal Server Error: Unexpected server error.
6. API to Delete Employee
ENDPOINT URL
picafepos/api/v1/employees/delete?employeeId=1
HTTP METHOD
DELETE
REQUEST PARAMETERS
{
"employee_id": "1"
}
● employee_id (required): ID of the employee to be deleted.
AUTHORIZATION
● Only authorized admin users should have access to this endpoint.
RESPONSE BODY
{
"message": "Employee deleted successfully"
}
RESPONSE CODES
● 200 OK: Employee deleted successfully.
● 401 Unauthorized: Unauthorized access (user is not an admin).
● 404 Not Found: Employee with specified ID not found.
● 500 Internal Server Error: Unexpected server error.

7. API to Create Employee
ENDPOINT URL
picafepos/api/v1/employees
HTTP METHOD
POST
REQUEST BODY
{
"storeId": 10,
"name": "anshi kishan",
"password": "*45rgeukMc",
"salary": 160600,
"position": "Cashier",
"managerId": 69
}
● name (required): Employee's name.
● salary(required): Employee's Salary.
● role (required): Employee's role in the system.
AUTHORIZATION
● Only authorized admin users should have access to this endpoint.
RESPONSE BODY
{
"employee_id": 1,
"message": "Employee successfully created"
}
RESPONSE CODES
● 201 Created: Employee created successfully.
● 401 Unauthorized: Unauthorized access (user is not an admin).
● 400 Bad Request: Invalid input data.
● 500 Internal Server Error: Unexpected server error.

8. API to Edit Employee Details
ENDPOINT URL
picafepos/api/v1/employees/edit/1
HTTP METHOD
PUT
REQUEST PARAMETERS
employee_id: 1
REQUEST BODY
{
"name": "Himanshi khurana",
"password": "@^fhwufehGkCsBJU",
"salary": 10000,
"manager_id": 69
}
AUTHORIZATION
● Only authorized admin users should have access to this endpoint.
RESPONSE BODY
{
"message": "Employee details updated successfully"
}
RESPONSE CODES
● 200 OK: Employee details updated successfully.
● 401 Unauthorized: Unauthorized access (user is not an admin).
● 404 Not Found: Employee with specified ID not found.
● 500 Internal Server Error: Unexpected server error.

9. API To get Employee
ENDPOINT URL
picafepos/api/v1/employees/store?store=1
HTTP METHOD
GET
REQUEST PARAMETERS
store: 1
AUTHORIZATION
● Only authorized admin users should have access to this endpoint.
RESPONSE BODY
[
{
"employee_id": 69,
"name": "Nirvi Wason",
"salary": 26665.0,
"position": "Manager"
},
{
"employee_id": 70,
"name": "Jayant Das",
"salary": 14082.0,
"position": "Cashier"
},
{
"employee_id": 71,
"name": "Nakul Ramakrishnan",
"salary": 14682.0,
"position": "Cashier"

},
{
"employee_id": 72,
"name": "Dharmajan Raja",
"salary": 24045.0,
"position": "Chef"
},
{
"employee_id": 73,
"name": "Renee Dalal",
"salary": 17864.0,
"position": "Chef"
},
{
"employee_id": 74,
"name": "Biju Kashyap",
"salary": 24340.0,
"position": "Chef"
}
]
RESPONSE CODES
● 200 OK: Employee details updated successfully.
● 401 Unauthorized: Unauthorized access (user is not an admin).
● 404 Not Found: Employee with specified ID not found.
● 500 Internal Server Error: Unexpected server error.
