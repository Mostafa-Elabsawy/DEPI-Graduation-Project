# 4. System Analysis & Design

---

## 1. Problem Statement & Objectives

### Problem Statement
The rapid growth of online shopping has created a strong demand for scalable, secure, and user-friendly e-commerce platforms. Many existing systems suffer from poor user experience, limited scalability, weak security, and lack of personalization.

This project aims to design and implement a modern e-commerce application that provides a seamless shopping experience, ensures secure transactions, and supports scalability using Angular for the frontend and ASP.NET Core Web API for the backend.

---
### Objectives
- Provide a smooth and intuitive shopping experience  
- Enable secure authentication and authorization  
- Support efficient product browsing and searching  
- Implement reliable order and payment processing  

---

## Actors & Use Cases

## Guest User

The guest user is an unregistered or not logged-in visitor who can explore the system but has limited functionality.

### Use Cases
- **Browse Products**  
  Allows viewing all available products in the system.

- **Search Products**  
  Enables searching using keywords, categories, or filters.

- **View Product Details**  
  Displays detailed product information such as price, description, and reviews.

- **Register Account**  
  Allows creating a new account to access full system features.

---

## Registered User

A registered user is a customer who has created an account and logged into the system.

### Use Cases
- **Login / Logout**  
  Secure authentication and session management.

- **Manage Profile**  
  Update personal information such as name, email, and password.

- **Add to Cart**  
  Add products to shopping cart for purchase.

- **Update Cart**  
  Modify product quantities in the cart.

- **Remove from Cart**  
  Remove items from the cart.

- **Add to Wishlist**  
  Save products for future purchase.

- **Checkout**  
  Validate cart and initiate order process.

- **Place Order**  
  Confirm purchase after successful payment.

- **Track Order**  
  View order status and progress.

- **Review Product**  
  Rate and review purchased products.

---

## Admin

The admin manages the system and ensures smooth operation.

### Use Cases
- **Manage Products**  
  Add, update, and delete products.

- **Manage Users**  
  View and manage user accounts.

- **Manage Orders**  
  Update and track order status.

- **View Reports**  
  Analyze sales and system performance.

---

## Payment Gateway

External system responsible for secure financial transactions.

### Use Cases
- **Process Payment**  
  Handle payment requests.

- **Confirm Transaction**  
  Return payment success or failure status.

---

## Functional Requirements
- JWT authentication  
- Product browsing and filtering  
- Cart and wishlist management  
- Order creation and tracking  
- Payment integration  
- Admin dashboard  

---

## Non-Functional Requirements
- Performance under 2 seconds response time  
- Scalability for thousands of users  
- Secure communication (HTTPS + JWT)  
- High availability (99.9%)  
- Responsive design  

---

## Software Architecture

### Architecture Style
- SPA (Angular) + REST API (.NET)

---

### System Layers
- Angular Frontend  
- ASP.NET Core Web API  
- Business Services Layer  
- Repository Layer (EF Core)  
- SQL Server Database  

---

### System Flow
User → Angular → API → Services → Database  

---

# 2. Database Design & Data Modeling

---

## ER Diagram Overview

The database is designed to store and manage all system data efficiently while maintaining relationships between entities.

---

## Entities

### User
- userId (PK)
- name
- email (unique)
- password
- role
- createdAt

---

### Product
- productId (PK)
- name
- description
- price
- stock
- imageUrl
- categoryId (FK)

---

### Category
- categoryId (PK)
- name

---

### Order
- orderId (PK)
- userId (FK)
- totalPrice
- status
- createdAt

---

### OrderItem
- orderItemId (PK)
- orderId (FK)
- productId (FK)
- quantity
- price

---

### Review
- reviewId (PK)
- userId (FK)
- productId (FK)
- rating
- comment
- createdAt

---

## Relationships

- User → Orders (One-to-Many)  
- Order → OrderItems (One-to-Many)  
- Product → Reviews (One-to-Many)  
- Category → Products (One-to-Many)  
- User → Reviews (One-to-Many)  

---

## 3. Data Flow & System Behavior

---

## System Overview (DFD)

The system interacts with:
- Users  
- Admins  
- Payment Gateway  

Data flows through the system and is stored in the database.

---

## Checkout Process (Sequence Flow)

- User initiates checkout  
- Frontend sends request to backend  
- Backend validates cart  
- Payment gateway processes payment  
- Order is created  
- Data is stored  
- Confirmation sent to user  

---

## Activity Flow

Start → Browse Products → Add to Cart → Checkout → Payment → Order Confirmation → End  

---

## Order State Lifecycle

- Created  
- Pending Payment  
- Paid  
- Shipped  
- Delivered  
- Cancelled  

---

## Class Diagram Overview

The system is built using modular classes representing real-world entities.

### User
Attributes: userId, name, email, password, role, createdAt  
Methods: register, login, logout, updateProfile  

---

### Product
Attributes: productId, name, description, price, stock, imageUrl, categoryId  
Methods: create, update, delete, getDetails  

---

### Order
Attributes: orderId, userId, totalPrice, status, createdAt  
Methods: createOrder, calculateTotal, updateStatus  

---

### OrderItem
Attributes: orderItemId, orderId, productId, quantity, price  
Methods: calculateSubtotal  

---

### Cart
Attributes: cartId, userId, items  
Methods: addItem, removeItem, updateQuantity, clearCart  

---

### Review
Attributes: reviewId, userId, productId, rating, comment, createdAt  
Methods: addReview, updateReview, deleteReview  

---

## Relationships Summary

- User has multiple Orders  
- Order contains multiple OrderItems  
- Product has multiple Reviews  
- Cart belongs to one User  

---

## 4. UI/UX Design & Prototyping

---

## Figma Prototype

The full UI/UX design is implemented in Figma, including wireframes, mockups, and interactive flows.

🔗 https://www.figma.com/file/your-project-link-here  

---

## Design Overview

The system UI is designed to provide a modern and smooth shopping experience.

### Included Screens
- Home Page  
- Product Listing  
- Product Details  
- Cart  
- Checkout  
- Login/Register  
---

## 5. System Deployment & Integration

---

## Technology Stack

### Frontend
- Angular (Standalone Components, Signals, Reactive Forms)

### Backend
- ASP.NET Core Web API  
- Services Layer  
- Repository Pattern  

### Database
- SQL Server  

---

## System Architecture Flow

User → Angular Frontend → .NET API → Services → Database  

---

## 6. API Documentation

The system provides RESTful APIs for:

- Authentication (Login, Register)  
- Product Management  
- Order Processing  

All endpoints follow standard HTTP conventions and return structured JSON responses.

---
