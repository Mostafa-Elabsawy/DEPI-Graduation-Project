# Requirements Gathering 
## Trendora - E-Commerce Web Application

---

# Stakeholder Analysis

## Identification of Stakeholders

| Stakeholder        | Description |
|-------------------|------------|
| Customers (Users) | End users who browse and purchase products |
| Guests            | Visitors who browse without registration |
| Admin             | Manages products, users, and orders |
| Development Team  | Builds and maintains the system |

---

## Stakeholder Needs

### Customers
- Easy product browsing and searching  
- Secure and fast checkout process  
- Clear product information  
- Responsive design (mobile-friendly)

### Guests
- Ability to browse products without login  
- View product details  

### Admin
- Full control over products (Add, Update, Delete)  
- Manage orders and users  
- Dashboard for monitoring system activity  

### Development Team
- Clear requirements  
- Scalable and maintainable system architecture  

---

# User Stories & Use Cases

## User Stories

- As a **user**, I want to browse products so that I can find items to buy.  
- As a **user**, I want to search and filter products so that I can quickly find what I need.  
- As a **user**, I want to add products to my cart so that I can purchase them later.  
- As a **user**, I want a secure checkout so that my payment information is protected.  
- As an **admin**, I want to manage products so that I can keep the catalog updated.  
- As an **admin**, I want to manage orders so that I can track and update their status.  

---

## Use Cases

### Use Case 1: User Registration/Login
- **Actor:** User  
- **Description:** User creates an account or logs into the system  
- **Outcome:** User gains access to full features  

### Use Case 2: Browse Products
- **Actor:** User / Guest  
- **Description:** User views available products  
- **Outcome:** Product list is displayed  

### Use Case 3: Add to Cart
- **Actor:** User  
- **Description:** User adds selected products to cart  
- **Outcome:** Product is stored in cart  

### Use Case 4: Checkout
- **Actor:** User  
- **Description:** User confirms order and completes payment  
- **Outcome:** Order is created successfully  

### Use Case 5: Manage Products (Admin)
- **Actor:** Admin  
- **Description:** Admin adds, edits, or deletes products  
- **Outcome:** Product catalog is updated  

---

# Functional Requirements
## Product Catalog
- The system shall display all products  
- The system shall allow filtering by category, brand, and price  
- The system shall provide product details

## Shopping Cart
- The system shall allow users to add products to cart  
- The system shall allow updating product quantity  
- The system shall allow removing items

## Checkout System
- The system shall calculate total price  
- The system shall allow order placement  
- The system shall handle payment processing
  
## Order Management
- The system shall store order information  
- The system shall allow users to view their orders  
- The system shall allow admin to update order status
  
## Authentication
- The system shall allow users to register and log in  
- The system shall validate user credentials  
- The system shall allow users to log out  

## Admin Panel
- The system shall allow admin to manage:
- Products  
- Categories  
- Users  
- Orders  

---

# Non-Functional Requirements

## Performance
- Page load time shall not exceed 3 seconds  
- System shall handle multiple users concurrently  

## Security
- The system shall use JWT authentication  
- The system shall protect against SQL Injection and XSS  
- Sensitive data shall be encrypted  

## Usability
- The system shall have a simple and intuitive UI  
- The system shall be fully responsive across devices  

## Reliability
- The system shall operate with minimal downtime  
- The system shall handle errors gracefully  
