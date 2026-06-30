# Online Animal Marketplace - Online Animal Marketplace
## Final Year Project (FYP)

### Project Overview
A full-featured Django web application for buying and selling animals online, built for Pakistan's market. Features 3 separate role-based dashboards (Buyer, Seller, Admin) with complete functionality.

---

## Features

### For Buyers
- Browse & search animals by category, breed, price, location
- Filter and sort listings
- Save favorites
- Message sellers directly
- Track purchases & transactions
- Leave reviews for sellers

### For Sellers
- Post animal listings (with images)
- Manage listings (edit/delete)
- View all sales & earnings
- Respond to buyer messages
- Track pending/confirmed sales
- Public seller profile page

### Admin Dashboard
- Approve/reject animal listings
- Verify seller accounts (CNIC-based)
- View & resolve reports
- Manage all users
- Platform analytics & statistics

---

## Setup Instructions

### 1. Install Dependencies
```bash
pip install django pillow
```

### 2. Run Migrations
```bash
cd animal_marketplace
python manage.py migrate
```

### 3. Create Superuser (Optional - test accounts pre-created)
```bash
python manage.py createsuperuser
```

### 4. Seed Categories & Test Accounts
```bash
python manage.py seed_data
```

### 5. Run Development Server
```bash
python manage.py runserver
```

Open: http://127.0.0.1:8000

---

## Test Accounts

| Role   | Username | Password   |
|--------|----------|------------|
| Admin  | admin    | admin123   |
| Seller | seller1  | seller123  |
| Buyer  | buyer1   | buyer123   |

---

## Project Structure
```
animal_marketplace/
├── animal_marketplace/     # Django project settings
│   ├── settings.py
│   └── urls.py
├── core/                   # Main application
│   ├── models.py           # Database models (User, Animal, etc.)
│   ├── views.py            # All view functions
│   ├── forms.py            # Django forms
│   ├── urls.py             # URL routing
│   └── admin.py            # Admin panel config
├── templates/              # HTML templates
│   ├── base.html           # Base layout
│   ├── home.html           # Landing page
│   ├── auth/               # Login, Register
│   ├── listings/           # Browse, Detail, Add/Edit
│   ├── dashboards/         # Buyer, Seller, Admin dashboards
│   ├── messages/           # Inbox, Conversation
│   ├── transactions/       # Transaction list
│   └── profile/            # Profile edit, Seller public profile
├── static/                 # CSS/JS/Images
├── media/                  # User uploaded files
└── db.sqlite3              # SQLite database
```

---

## Models (from Class Diagram)
- **User** - Base user with role (buyer/seller/admin)
- **SellerProfile** - CNIC docs, business name, rating
- **BuyerProfile** - Shipping address, favorites count
- **Animal** - Title, breed, price, images, location, status
- **AnimalCategory** - Cattle, Goats, Sheep, Poultry, etc.
- **Message** - Buyer-seller messaging
- **Transaction** - Purchase records with status tracking
- **Review** - Ratings & comments for sellers
- **Report** - Flag inappropriate listings
- **Favorite** - Saved animals for buyers

---

## Tech Stack
- **Backend**: Django 4.x
- **Database**: SQLite (dev) / PostgreSQL (production)
- **Frontend**: Bootstrap 5, Font Awesome, Poppins (Google Fonts)
- **Image Handling**: Pillow
