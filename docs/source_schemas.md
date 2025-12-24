# Source Schemas

## Sales Orders

| Column Name | Data Type | Description |
|-----------|----------|-------------|
| order_id | STRING | Unique order identifier |
| order_ts | TIMESTAMP | Order creation timestamp |
| customer_id | STRING | Customer identifier |
| product_id | STRING | Product identifier |
| quantity | INT | Number of units ordered |
| unit_price | DECIMAL(10,2) | Price per unit |
| discount | DECIMAL(10,2) | Discount applied |
| region | STRING | Sales region |

## Customers

| Column Name | Data Type | Description |
|------------|----------|-------------|
| customer_id | STRING | Unique customer ID |
| customer_name | STRING | Customer name |
| email | STRING | Email address |
| signup_date | DATE | Signup date |
| region | STRING | Customer region |

## Products

| Column Name | Data Type | Description |
|------------|----------|-------------|
| product_id | STRING | Product ID |
| product_name | STRING | Product name |
| category | STRING | Product category |
| price | DECIMAL(10,2) | Product price |


## User Behavior Events

| Column Name | Data Type | Description |
|------------|----------|-------------|
| event_id | STRING | Unique event identifier |
| event_ts | TIMESTAMP | Event timestamp |
| user_id | STRING | User identifier |
| session_id | STRING | User session ID |
| event_type | STRING | LOGIN / ADD_TO_CART / PURCHASE |
| product_id | STRING | Product involved (nullable) |
| device_type | STRING | Mobile / Web |
| platform | STRING | Android / iOS / Web |


