# 🌿 Fog & Fern SF

A full-stack ecommerce website for a premium San Francisco plant shop. Fog & Fern SF provides a responsive storefront, customer accounts, shopping cart and checkout, Square card payments, branded receipts, order tracking, and a complete administration dashboard.

![Node.js](https://img.shields.io/badge/Node.js-20%2B-339933?logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-5-000000?logo=express&logoColor=white)
![EJS](https://img.shields.io/badge/EJS-Templates-B4CA65?logo=ejs&logoColor=black)
![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?logo=sqlite&logoColor=white)
![Square](https://img.shields.io/badge/Square-Payments-006AFF?logo=square&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 📖 About the Project

Fog & Fern SF is a dynamic plant-shop web application built for a professional local retail business. Customers can browse plants, search and filter products, create an account, manage a cart, choose delivery or pickup, pay securely, and view their previous orders.

Administrators receive a protected dashboard for managing products, categories, inventory, customer orders, fulfillment statuses, and contact messages.

---

## ✨ Main Features

### 🛍️ Customer Storefront

- Responsive premium plant-shop homepage
- Dynamic featured products and categories
- Product search and category filtering
- Pet-safe product filtering
- Product sorting options
- Detailed product pages
- Plant descriptions and care requirements
- Customer product reviews
- Plant-care, services, delivery, about, and policy pages
- Contact form and newsletter subscription

### 🛒 Shopping Cart and Checkout

- Session-based shopping cart
- Add, update, remove, and clear cart items
- Live order summary
- Local San Francisco delivery
- Free delivery for orders of **$75 or more**
- **$9 delivery fee** for smaller delivery orders
- Free store pickup
- Automatic **8.625% tax** calculation
- Customer notes during checkout
- Inventory reduction after successful orders

### 💳 Payment System

- Square Web Payments SDK integration
- Secure card tokenization in the browser
- Square Sandbox support for development and testing
- Pay-on-delivery or pay-at-pickup option
- Payment status tracking
- Card brand and last four digits display
- Square payment and receipt information stored with the order
- Raw card details are never stored by the application

### 🧾 Order Confirmation and Receipts

- Premium order-confirmation page
- Unique order number generation
- Estimated delivery or pickup information
- Detailed product and pricing breakdown
- Subtotal, tax, delivery fee, and total display
- Branded printable receipt
- Receipt QR code
- Browser print and PDF-save support
- Customer order-history page
- Detailed account order view

### 👤 Customer Accounts

- Customer registration and login
- Secure password hashing with bcrypt
- Session-based authentication
- Profile information updates
- Customer dashboard
- Order history
- Protected order details
- Role-based customer and administrator access

### 🛠️ Administration Dashboard

- Protected administrator login and routes
- Dashboard statistics
- Product inventory management
- Add, edit, feature, hide, and delete products
- Upload product images
- Use externally hosted product image URLs
- Category creation and management
- Low-stock visibility
- View all customer orders
- View complete order details
- Update order fulfillment status
- Review customer contact messages
- Mark messages as read

---

## 🧰 Technology Stack

### Backend

- Node.js
- Express.js 5
- better-sqlite3
- Express Session
- connect-flash
- express-validator
- bcrypt
- Multer
- dotenv

### Frontend

- EJS
- express-ejs-layouts
- HTML5
- CSS3
- Vanilla JavaScript
- Font Awesome
- Responsive custom interface

### Payments

- Square Web Payments SDK
- Square Payments API

### Database

- SQLite
- Automatic database initialization and sample-data seeding

---

## 📁 Project Structure

```text
fog-and-fern-sf/
├── config/
│   └── database.js              # Database setup, schema, and seed data
├── controllers/
│   ├── accountController.js     # Customer profile and order history
│   ├── adminController.js       # Admin dashboard and management actions
│   ├── authController.js        # Registration, login, and logout
│   ├── cartController.js        # Shopping-cart operations
│   ├── checkoutController.js    # Checkout, Square payments, and receipts
│   ├── homeController.js        # Homepage and informational pages
│   └── shopController.js        # Catalog, filters, details, and reviews
├── middleware/
│   ├── adminMiddleware.js
│   ├── authMiddleware.js
│   ├── cartMiddleware.js
│   └── uploadMiddleware.js
├── models/
│   ├── Cart.js
│   ├── Category.js
│   ├── Order.js
│   ├── Product.js
│   └── User.js
├── public/
│   ├── css/
│   │   └── style.css
│   └── js/
│       ├── checkout.js
│       └── main.js
├── routes/
│   ├── accountRoutes.js
│   ├── adminRoutes.js
│   ├── authRoutes.js
│   ├── cartRoutes.js
│   ├── checkoutRoutes.js
│   ├── homeRoutes.js
│   └── shopRoutes.js
├── uploads/
│   └── products/                # Administrator-uploaded product images
├── views/
│   ├── account/
│   ├── admin/
│   ├── auth/
│   ├── cart/
│   ├── checkout/
│   ├── layouts/
│   ├── pages/
│   ├── partials/
│   └── shop/
├── .env.example
├── .gitignore
├── app.js                       # Express application entry point
├── package.json
└── README.md
```

---

## 🚀 Local Installation

### Prerequisites

Install the following before running the project:

- Node.js 20 or newer
- npm
- A Square Developer account for card-payment testing

### 1. Open the project folder

```bash
cd fog-and-fern-sf
```

### 2. Install dependencies

```bash
npm install
```

Do not manually upload or copy the `node_modules` folder. It is generated by `npm install`.

### 3. Create the environment file

On Windows Command Prompt:

```cmd
copy .env.example .env
```

On PowerShell, macOS, or Linux:

```bash
cp .env.example .env
```

### 4. Configure environment variables

Open `.env` and update the values:

```env
PORT=3000
NODE_ENV=development
SESSION_SECRET=replace-with-a-long-random-secret

ADMIN_EMAIL=admin@fogandfernsf.com
ADMIN_PASSWORD=Admin123!

SQUARE_ENVIRONMENT=sandbox
SQUARE_APPLICATION_ID=sandbox-sq0idb-your-application-id
SQUARE_LOCATION_ID=your-sandbox-location-id
SQUARE_ACCESS_TOKEN=your-private-sandbox-access-token
SQUARE_API_VERSION=2026-05-20
```

Generate a strong session secret instead of using the sample value.

### 5. Start the application

Development mode with automatic restart:

```bash
npm run dev
```

Production-style start:

```bash
npm start
```

### 6. Open the website

```text
http://localhost:3000
```

The SQLite database and sample catalog are initialized automatically when the application starts.

---

## 🔐 Default Administrator Login

Unless changed in `.env`:

```text
Email: admin@fogandfernsf.com
Password: Admin123!
```

Change these credentials before deployment.

When starting with a clean database and new administrator credentials, remove the local SQLite database files and restart the application so initialization can run again.

---

## 💳 Square Sandbox Setup

1. Sign in to the Square Developer Dashboard.
2. Create or open a Square application.
3. Select the **Sandbox** environment.
4. Copy the Sandbox Application ID.
5. Copy or regenerate the Sandbox Access Token.
6. Find the Sandbox Location ID.
7. Add the credentials to `.env`.
8. Restart the Node.js server.
9. Add a product to the cart and proceed to checkout.

### Sandbox card testing

Square Sandbox does not accept normal real-world card numbers. Use a card number from Square's official Sandbox test values.

A commonly used successful Sandbox Visa test number is:

```text
4111 1111 1111 1111
```

Use a future expiration date, a valid-looking CVV, and a valid postal code supported by Square's test documentation.

> Never use a real customer's card information while the application is configured for Sandbox.

---

## 🌐 Available Routes

| Area | Route | Purpose |
|---|---|---|
| Home | `/` | Main storefront |
| Shop | `/shop` | Product catalog |
| Cart | `/cart` | Shopping cart |
| Checkout | `/checkout` | Delivery, pickup, and payment |
| Login | `/auth/login` | Customer or admin login |
| Register | `/auth/register` | Customer account creation |
| Account | `/account` | Customer dashboard |
| Orders | `/account/orders` | Customer order history |
| Admin | `/admin` | Administration dashboard |
| Contact | `/contact` | Customer contact form |
| Plant Care | `/plant-care` | Plant-care guide |
| Services | `/services` | Shop services |
| Delivery | `/delivery` | Delivery and pickup information |

---

## 🗄️ Database Notes

The project uses SQLite for simple local development and demonstration deployment.

The database stores information such as:

- Users and administrator accounts
- Products and categories
- Shopping and order information
- Order items
- Payment status and Square transaction references
- Product reviews
- Contact messages
- Newsletter subscriptions

The following generated files should normally remain outside version control:

```text
.env
node_modules/
plant-shop.db-shm
plant-shop.db-wal
```

Consider excluding the main database file from a public repository when it contains real customer or order data.

---

## ☁️ Deployment

Use the following general settings on a Node.js hosting provider:

```text
Build command: npm install
Start command: npm start
```

Add every required `.env` value through the hosting provider's environment-variable settings.

### Important SQLite limitation

SQLite requires persistent storage. Some cloud hosts erase local files during redeployment or restart. For a production ecommerce website, use persistent disk storage or migrate the database to a managed system such as PostgreSQL.

### Production payment checklist

Before accepting real payments:

- Set `SQUARE_ENVIRONMENT=production`
- Use production Square credentials
- Use the correct production Location ID
- Deploy the site over HTTPS
- Configure secure session cookies
- Use a persistent production database
- Protect all environment secrets
- Verify tax, refund, privacy, and fulfillment policies
- Test payment errors and webhook handling

---

## 🔒 Security Notes

- Never commit the `.env` file.
- Never publish a Square access token.
- Regenerate any credential that has been shared publicly.
- Change the default administrator password.
- Use a long random session secret.
- Keep dependencies updated.
- Validate uploaded files and customer input.
- Use HTTPS in production.
- Do not store raw payment-card details.
- Back up the production database securely.

---

## 📸 Screenshots

Create a `screenshots` folder and add project images using names such as:

```text
screenshots/home.png
screenshots/shop.png
screenshots/product-details.png
screenshots/cart.png
screenshots/checkout.png
screenshots/order-confirmation.png
screenshots/receipt.png
screenshots/customer-orders.png
screenshots/admin-dashboard.png
```

Then add them to this README:

```md
## Home Page

![Fog & Fern home page](screenshots/home.png)

## Checkout

![Fog & Fern checkout](screenshots/checkout.png)

## Branded Receipt

![Fog & Fern branded receipt](screenshots/receipt.png)

## Admin Dashboard

![Fog & Fern admin dashboard](screenshots/admin-dashboard.png)
```

GitHub paths are case-sensitive. The folder and filename in the Markdown must exactly match the uploaded file.

---

## 🧪 Useful Commands

```bash
# Install dependencies
npm install

# Run in development mode
npm run dev

# Run normally
npm start

# Check dependency security notices
npm audit

# Apply compatible dependency fixes
npm audit fix
```

---

## 🔮 Possible Future Improvements

- Square webhook verification
- Automated email receipts
- Password reset by email
- Email verification
- Product wish list
- Discount and coupon system
- Advanced inventory alerts
- Delivery-zone validation
- Real delivery scheduling
- Sales analytics and downloadable reports
- PostgreSQL production migration
- Automated testing
- Docker support

---

## 👨‍💻 Author

**Shahrier Emon Shanto**

- GitHub: `cloud-pantheon`
- Computer Science student at Independent University, Bangladesh

---

## 📄 License

This project is licensed under the MIT License.

---

<p align="center">
  Built with 🌿 for plant lovers in San Francisco.
</p>
