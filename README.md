🛒 E-Commerce API (Django + DRF + JWT)

A RESTful E-Commerce Backend API built with Django REST Framework (DRF) and JWT Authentication.
This project provides the core backend functionalities of an online shopping platform including user authentication, product management, carts, orders, and checkout.

🚀 Features

User Authentication (JWT)

Register, Login, Logout

Role-based access (Admin, Vendor, Customer)

Product Management

Add, update, delete products (Admin/Vendor)

Search, filter, and paginate product list

Cart Management

Add, update, and remove cart items

Each user has their own cart

Order Management

Place orders directly from the cart

Order status: pending → confirmed → delivered

Automatic total price calculation

Checkout

Simulated payment gateway

Order confirmation

Reviews & Ratings (Optional)

Customers can leave reviews on purchased products

🛠️ Tech Stack

Backend Framework: Django 5, Django REST Framework

Authentication: JWT (djangorestframework-simplejwt)

Database: SQLite (default) / PostgreSQL (production ready)

Containerization: Docker (optional)

API Docs: Swagger / DRF Browsable API

⚙️ Installation & Setup
1️⃣ Clone Repository
git clone https://github.com/yourusername/ecommerce-api.git
cd ecommerce-api

2️⃣ Create Virtual Environment
python -m venv venv
source venv/bin/activate   # (Linux/Mac)
venv\Scripts\activate      # (Windows)

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Configure Django

In settings.py, set custom user model:

AUTH_USER_MODEL = 'shop.User'

5️⃣ Apply Migrations
python manage.py makemigrations
python manage.py migrate

6️⃣ Create Superuser
python manage.py createsuperuser

7️⃣ Run Server
python manage.py runserver


Server runs on:
👉 http://127.0.0.1:8000/

🔑 API Endpoints
🔐 Authentication

POST /api/users/ → Register new user

POST /api/token/ → Login (get JWT access & refresh tokens)

POST /api/token/refresh/ → Refresh token

📦 Products

GET /api/products/ → List products

POST /api/products/ → Add product (Vendor/Admin only)

PUT /api/products/{id}/ → Update product

DELETE /api/products/{id}/ → Delete product

🛒 Cart

GET /api/carts/ → View user cart

POST /api/carts/ → Create cart

POST /api/cartitems/ → Add item to cart

📑 Orders

POST /api/orders/ → Create order

GET /api/orders/ → View user orders

POST /api/orders/{id}/checkout/ → Checkout order

🔍 Testing with Postman

Register user → POST /api/users/

Login → POST /api/token/ → copy access token

In Postman, set Authorization header:

Authorization: Bearer <access_token>


Now test Products → Cart → Orders → Checkout


✅ Future Improvements

Integrate real payment gateways (Stripe, PayPal)

Add inventory tracking system

Enable email notifications for order confirmation

Implement unit tests (pytest)

👨‍💻 Author

Bibek Shah
Backend Developer | Django & DRF Enthusiast