# Med-Store Management System

A Django-based pharmacy management system that helps manage medicine inventory, patient records, and billing operations for medical stores.

## 🏥 Features

- **User Authentication**: Secure login system for pharmacy staff
- **Medicine Management**: Add, view, and manage medicine inventory with details like:
  - Medicine name, dosage, and composition
  - Stock levels and expiry dates
  - Manufacturer information
  - Pricing
- **Patient Management**: Store and manage patient information including:
  - Personal details (name, age, gender)
  - Contact information (phone, address)
- **Billing System**: Complete billing functionality with:
  - Dynamic medicine selection and quantity input
  - Automatic bill generation with total calculation
  - Bill history and tracking
- **Inventory Tracking**: Automatic stock deduction upon medicine purchase

## 🛠 Technology Stack

- **Backend**: Django 3.2.4
- **Database**: SQLite3
- **Frontend**: HTML5, CSS3, JavaScript
- **Styling**: Bootstrap 4.4.1
- **Authentication**: Django's built-in authentication system

## 📁 Project Structure

```
Med-store/
├── manage.py                 # Django management script
├── db.sqlite3               # SQLite database
├── med_store/               # Main project directory
│   ├── settings.py          # Django settings
│   ├── urls.py             # Main URL configuration
│   ├── wsgi.py             # WSGI configuration
│   └── asgi.py             # ASGI configuration
└── store/                   # Main application
    ├── models.py           # Database models
    ├── views.py            # View functions
    ├── urls.py             # App URL patterns
    ├── admin.py            # Admin configuration
    ├── templates/store/    # HTML templates
    │   ├── layout.html     # Base template
    │   ├── login.html      # Login page
    │   ├── billing.html    # Billing interface
    │   ├── bills.html      # Bill history
    │   ├── add.html        # Add medicine form
    │   └── view.html       # View medicines
    ├── static/store/       # Static files
    │   ├── my.css          # Custom styles
    │   └── myscript.js     # JavaScript functionality
    └── migrations/         # Database migrations
```

## 📊 Database Schema

### Models Overview

1. **User**: Extended Django user model for authentication
2. **Manufacture**: Stores manufacturer information
3. **Medicine**: Medicine inventory with stock and pricing
4. **Patient**: Customer/patient records
5. **Bill**: Billing records with timestamps
6. **Buy**: Individual medicine purchases within a bill

### Key Relationships

- Medicine → Manufacturer (Many-to-One)
- Bill → Patient (Many-to-One)
- Buy → Bill (Many-to-One)
- Buy → Medicine (Many-to-One)

## 🚀 Installation & Setup

### Prerequisites

- Python 3.7+
- Django 3.2.4
- SQLite3 (included with Python)

### Installation Steps

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd Med-store
   ```

2. **Install Django** (if not already installed)

   ```bash
   pip install django==3.2.4
   ```

3. **Apply database migrations**

   ```bash
   python manage.py migrate
   ```

4. **Create a superuser** (optional, for admin access)

   ```bash
   python manage.py createsuperuser
   ```

5. **Run the development server**

   ```bash
   python manage.py runserver
   ```

6. **Access the application**
   - Open your browser and go to `http://127.0.0.1:8000/`
   - Login with your credentials to access the system

## 📝 Usage Guide

### Getting Started

1. **Login**: Access the system through the login page
2. **Add Manufacturers**: First, add manufacturer information through Django admin
3. **Add Medicines**: Use the "ADD MED" section to add medicines to inventory
4. **View Inventory**: Check current medicine stock in "VIEW MED"
5. **Process Bills**: Use "BILLING" to create new customer bills
6. **Track History**: View all past bills in "BILLS" section

### Billing Process

1. Enter patient information (name, age, gender, phone, address)
2. Select medicines from the dropdown
3. Enter quantities for each medicine
4. Click "Add" to add medicines to the bill
5. Submit the form to generate the final bill
6. Stock levels are automatically updated

## 🔧 Configuration

### Key Settings

- **Database**: SQLite3 (configured in `settings.py`)
- **Authentication**: Custom User model (`store.User`)
- **Debug Mode**: Currently enabled (set `DEBUG = False` for production)
- **Static Files**: Served from `/static/` URL

### Security Considerations

⚠️ **Important for Production**:

- Change the `SECRET_KEY` in `settings.py`
- Set `DEBUG = False`
- Configure `ALLOWED_HOSTS`
- Use a production database (PostgreSQL/MySQL)
- Implement HTTPS
- Add proper error handling and logging

## 🌟 Key Features in Detail

### Dynamic Billing Interface

- Real-time medicine selection with JavaScript
- Automatic stock deduction
- Dynamic form updates without page refresh

### Inventory Management

- Track medicine expiry dates
- Monitor stock levels
- Manufacturer relationship tracking

### Patient Records

- Comprehensive patient information storage
- Bill history per patient
- Contact information management

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 📞 Support

For support or questions about this pharmacy management system, please:

- Open an issue in the repository
- Contact the development team
- Check the Django documentation for framework-related questions

## 🔮 Future Enhancements

Potential improvements for the system:

- Medicine expiry date alerts
- Advanced reporting and analytics
- Prescription management
- Multi-location support
- Mobile-responsive design improvements
- Barcode scanning integration
- Automated reorder notifications

---

**Note**: This system is designed for educational and small-scale pharmacy management purposes. For production use, please implement additional security measures and testing.
