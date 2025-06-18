# Zero Waste Management System

A comprehensive backend system for managing waste collection, recycling, and environmental sustainability initiatives.

## 🚀 Features

- User Authentication and Authorization
- Profile Management with Image Upload
- Email Notifications
- Payment Integration (Paystack)
- Waste Collection Scheduling
- Recycling Points Management
- Environmental Impact Tracking

## 🛠️ Technology Stack

- **Framework**: FastAPI
- **Database**: PostgreSQL with SQLModel
- **Authentication**: JWT (JSON Web Tokens)
- **Email**: FastAPI-Mail
- **File Storage**: Local Storage
- **Payment**: Paystack Integration
- **Dependency Management**: Poetry

## 📋 Prerequisites

- Python 3.12 or higher
- Poetry (Python package manager)
- PostgreSQL database
- SMTP server access (for email functionality)
- Paystack account (for payment processing)

## 🔧 Installation

1. Clone the repository:
```bash
git clone https://github.com/NwoluDavid/ZERO_WASTE_BACKEND.git
cd ZERO_WASTE_BACKEND
```

2. Install dependencies using Poetry:
```bash
poetry install
```

3. Create a `.env` file in the root directory with the following variables:
```env
# API Settings
PROJECT_NAME="ZERO WASTE"
FRONTEND_URL="http://localhost:8000/api/v1/"
API_V1_STR="/api/v1"
SECRET_KEY="your-secret-key-here"
DOMAIN="localhost"
ENVIRONMENT="local"

# CORS Settings
BACKEND_CORS_ORIGINS=["http://localhost:8000","http://localhost:3000"]

# Email Settings
EMAILS_FROM_NAME="ZERO WASTE"
EMAILS_FROM_EMAIL="your-email@example.com"
SMTP_TLS=True
SMTP_SSL=True
SMTP_PORT=2525
SMTP_HOST="smtp.gmail.com"
SMTP_USER="your-email@gmail.com"
SMTP_PASSWORD="your-app-specific-password"

# Payment Settings
PAYMENT_URL="https://api.paystack.co"
PAYSTACK_SECRET_KEY="your-paystack-secret-key"
```

4. Set up the database:
```bash
# Create database migrations
alembic revision --autogenerate -m "Initial migration"

# Apply migrations
alembic upgrade head
```

## 🚀 Running the Application

1. Start the development server:
```bash
poetry run uvicorn main:app --reload
```

2. Access the API documentation:
- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

## 📁 Project Structure

```
ZERO_WASTE_BACKEND/
├── app/
│   ├── api/            # API routes and endpoints
│   ├── templates/      # HTML templates
│   ├── email-templates/# Email templates
│   ├── models.py       # Database models
│   ├── schemas.py      # Pydantic schemas
│   ├── crud.py         # CRUD operations
│   ├── config.py       # Application configuration
│   ├── deps.py         # Dependency injection
│   └── utils.py        # Utility functions
├── profile_pictures/   # User profile images
├── main.py            # Application entry point
├── alembic.ini        # Database migration config
└── pyproject.toml     # Project dependencies
```

## 🔐 API Authentication

The API uses JWT (JSON Web Tokens) for authentication. Include the token in the Authorization header:

```
Authorization: Bearer <your_token>
```

## 📧 Email Configuration

The system uses FastAPI-Mail for sending emails. Configure your SMTP settings in the `.env` file:

- For Gmail, you'll need to:
  1. Enable 2-factor authentication
  2. Generate an App Password
  3. Use the App Password in SMTP_PASSWORD

## 💳 Payment Integration

The system integrates with Paystack for payment processing. Configure your Paystack settings in the `.env` file:

1. Sign up for a Paystack account
2. Get your secret key from the Paystack dashboard
3. Add the secret key to PAYSTACK_SECRET_KEY in .env

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Authors

- **Daniel Nwolu** - *Initial work*

## 🙏 Acknowledgments

- FastAPI documentation
- SQLModel documentation
- Paystack API documentation