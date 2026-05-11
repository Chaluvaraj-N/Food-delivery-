

A Django-based **food delivery web application** where users can browse a menu, add items to a cart, place orders, and pay using **Cash on Delivery** or **Stripe online payment (test mode)**.

---

## ✨ Live Features

- 🛍️ **Browse menu items** with images and descriptions
- 🧺 **Add to cart** and update quantities
- 🧾 **Cart review** and total cost calculation
- ✅ **Place orders** with:
  - **Cash on Delivery**
  - **Online payment via Stripe**
- 📦 **My Orders** page with order history
- 🗑️ Ability to **delete orders**
- 📍 Address management (save multiple addresses per user)

---

## 🧠 Tech Stack

- **Backend:** Django 4.x
- **Frontend:** HTML, CSS, JavaScript
- **Database:** SQLite (default)
- **Payments:** Stripe API (test mode)

---

## 📁 Project Structure

```text
fooddelivery/
├── manage.py
├── fooddelivery/
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── orders/
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── migrations/
│   └── templates/
│       ├── home.html
│       ├── cart.html
│       ├── address.html
│       ├── confirm_order.html
│       └── my_orders.html
├── static/
│   ├── style.css
│   └── script.js
└── media/
    └── food_images/
```

---

## 🚀 Setup & Run

### 1) Clone the repository

```bash
git clone https://github.com/Chaluvaraj-N/Food-delivery-.git
cd fooddelivery
```

### 2) Install dependencies

```bash
pip install -r requirements.txt
```

### 3) Configure Stripe (important)

Stripe secret keys must **not** be hardcoded.

1. Create a Stripe account and use **test mode**.
2. Get your secret key from Stripe dashboard.
3. Configure it as Django setting (recommended):

In `fooddelivery/settings.py`, set:
- `STRIPE_SECRET_KEY = "sk_test_..."`

Or via environment variable (preferred):
- Update settings to read environment variables (example below):

```python
STRIPE_SECRET_KEY = os.getenv("STRIPE_SECRET_KEY")
```

Then set it locally:

```bash
set STRIPE_SECRET_KEY=sk_test_...
```

### 4) Migrate the database

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5) (Optional) Create a superuser

```bash
python manage.py createsuperuser
```

### 6) Run the development server

```bash
python manage.py runserver
```

Open:
- http://127.0.0.1:8000/

Admin:
- http://127.0.0.1:8000/admin/

---

## 💳 Payment Flow

### Cash on Delivery
- Order is placed immediately after confirmation.

### Online Payment (Stripe)
- App creates a Stripe Checkout session
- User completes payment on Stripe
- After success, the app proceeds with order placement

---

## 🧾 Notes / Customization

- **Add/edit menu items** via Django admin.
- Food images are stored in `media/food_images/`.
- Address persistence is handled per user.

---

## 🛡️ Security Reminder

- Do not commit real Stripe secret keys or other credentials to the repository.
- Keep `DEBUG=False` and configure `ALLOWED_HOSTS` for production deployments.

---

## 📜 License

MIT License

---

## 🙌 Credits

- Django: https://www.djangoproject.com/
- Stripe: https://stripe.com/

