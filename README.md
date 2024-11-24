## SavorySprint

Savory Sprint is a web-based food delivery platform that allows customers to explore a variety of menu items and order their favorite dishes. Users can browse through the menu, add items to their cart, and place orders seamlessly. The platform provides real-time order tracking, displaying statuses like "Food Preparing," "On the Way," and "Delivered." Customers can choose to pay through cash on delivery or via online payments using the Stripe payment gateway, ensuring a convenient and hassle-free experience.

---

## Features

- **User Authentication:**
  - Secure user registration and login using JSON Web Tokens (JWT).
  - Passwords are securely hashed using bcrypt.

- **Menu Exploration:**
  - Browse through a dynamically loaded menu.
  - Filter and search for items by categories.

- **Cart Management:**
  - Add, update, or remove items from the cart.
  - Real-time cart updates.

- **Order Placement:**
  - Place orders with a simple checkout process.
  - Support for Cash on Delivery and online payments.

- **Order Tracking:**
  - Real-time updates for order status: *Food Preparing*, *On the Way*, and *Delivered*.

- **Payment Integration:**
  - Secure online payments using Stripe Payment Gateway.
  - Support for failed transaction handling.

- **Responsive Design:**
  - Fully responsive UI for mobile, tablet, and desktop devices.

---

## Technologies Used

### Frontend
- **React.js**: Component-based UI development.
- **Axios**: HTTP client for API requests.
- **CSS**: Styling and responsive design.

### Backend
- **Node.js**: Server-side JavaScript runtime.
- **Express.js**: Web framework for routing and middleware.
- **Mongoose**: ODM for MongoDB.

### Database
- **MongoDB**: Document-oriented NoSQL database for storing users, orders, and menu items.

### Payment Gateway
- **Stripe**: Secure online payment integration.

---

## Installation and Setup

### Prerequisites
Ensure you have the following installed:
- **Node.js** (v14+)
- **MongoDB** (local or cloud-based, e.g., MongoDB Atlas)

### Steps to Run the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/raviprakash7367/SavorySprint.git
   cd SavorySprint
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Add the following variables:
     ```plaintext
     PORT=5000
     MONGO_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     STRIPE_SECRET_KEY=your_stripe_secret_key
     ```

4. Start the server:
   ```bash
   npm start
   ```

5. Navigate to `http://localhost:5000` in your browser.

---

## API Endpoints

### Authentication
- **POST /api/auth/register**: Register a new user.
- **POST /api/auth/login**: Authenticate and log in a user.

### Menu
- **GET /api/menu**: Retrieve the list of menu items.

### Cart
- **POST /api/cart**: Add an item to the cart.
- **GET /api/cart**: Retrieve the user's cart.
- **DELETE /api/cart/:itemId**: Remove an item from the cart.

### Orders
- **POST /api/orders**: Place a new order.
- **GET /api/orders/:orderId**: Get the details of a specific order.
- **GET /api/orders**: Retrieve all orders for the logged-in user.

### Payments
- **POST /api/payments/stripe**: Process an online payment via Stripe.

---

## Project Workflow

1. **Landing on the Home Page:**
   - The frontend sends a `GET` request to `/api/menu` to fetch menu items.
   - The menu is displayed dynamically based on the response.

2. **Adding Items to the Cart:**
   - When a user adds an item to the cart, a `POST` request is sent to `/api/cart`.
   - The backend validates the request and updates the `Cart` collection.

3. **Placing an Order:**
   - A `POST` request to `/api/orders` initiates the order placement process.
   - If online payment is selected, the backend interacts with the Stripe API for payment confirmation.
   - On success, the `Orders` collection is updated, and the user receives an order confirmation.

4. **Tracking an Order:**
   - The order status is updated by the restaurant in the backend.
   
---

## Future Enhancements

- **Push Notifications**: Notify users of order status changes in real-time.
- **Advanced Analytics**: Provide detailed reports for restaurant owners.
- **Multi-Language Support**: Make the platform accessible to a wider audience.
- **Delivery Partner Module**: Introduce a module for delivery personnel to update statuses directly.

---




