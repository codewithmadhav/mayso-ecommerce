# 🎉 MAYSO E-Commerce Platform

**A Complete Production-Ready E-Commerce Solution for Fashion Brands**

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![Django](https://img.shields.io/badge/Django-4.2-darkgreen)
![Flutter](https://img.shields.io/badge/Flutter-latest-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-12+-blue)
![Docker](https://img.shields.io/badge/Docker-Ready-brightgreen)

---

## 📋 About MAYSO

MAYSO is a **complete e-commerce platform** designed specifically for clothing brands. This project provides:

- ✅ Full-featured Django backend with REST API
- ✅ Beautiful Flutter mobile app (iOS & Android)
- ✅ Razorpay payment integration (test mode first)
- ✅ Complete order management system
- ✅ Inventory tracking with variants
- ✅ PDF invoice generation
- ✅ Admin dashboard
- ✅ Docker deployment ready

---

## 🎯 Features

### Customer Features
- User registration & login
- Browse products with search & filter
- Product details with multiple images
- Size and color variants
- Shopping cart management
- Secure checkout
- Razorpay payment (test mode)
- Order confirmation
- Order tracking
- Invoice download
- Order history
- Address management

### Admin Features
- Dashboard with analytics
- Product management
- Category management
- Image upload (multiple per product)
- Inventory tracking
- Order management
- Order status updates
- Payment tracking
- Coupon management
- Sales analytics

---

## 🚀 Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/codewithmadhav/mayso-ecommerce.git
cd mayso-ecommerce
```

### 2. Backend Setup
```bash
cd backend
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# Setup environment
cp .env.example .env
# Edit .env with your database credentials

# Create database
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser

# Run server
python manage.py runserver
```

### 3. Flutter Setup
```bash
cd frontend/mayso_app
flutter pub get
flutter run
```

### 4. Docker Setup
```bash
docker-compose up -d
```

---

## 📚 Documentation

| Document | Purpose |
|----------|----------|
| [COMPLETE_ROADMAP_AND_QUICK_START.md](COMPLETE_ROADMAP_AND_QUICK_START.md) | Full project roadmap |
| [PHASE_1_PLANNING.md](PHASE_1_PLANNING.md) | Architecture & planning |
| [PHASE_2_BACKEND_SETUP_PART_A.md](PHASE_2_BACKEND_SETUP_PART_A.md) | Django models & setup |
| [PHASE_2_BACKEND_SETUP_PART_B.md](PHASE_2_BACKEND_SETUP_PART_B.md) | REST API endpoints |
| [PHASE_2_BACKEND_SETUP_PART_C.md](PHASE_2_BACKEND_SETUP_PART_C.md) | Payments & invoices |

---

## 🏗️ Project Structure

```
mayso-ecommerce/
├── backend/                 # Django Backend
│   ├── mayso_api/          # Django project settings
│   ├── apps/
│   │   ├── users/          # User authentication
│   │   ├── products/       # Product management
│   │   ├── categories/     # Categories
│   │   ├── cart/           # Shopping cart
│   │   ├── orders/         # Order management
│   │   ├── payments/       # Payment processing
│   │   ├── inventory/      # Stock management
│   │   └── analytics/      # Admin dashboard
│   ├── media/              # Uploaded files
│   ├── static/             # Static files
│   ├── requirements.txt
│   ├── manage.py
│   ├── Dockerfile
│   └── .env.example
│
├── frontend/               # Flutter App
│   └── mayso_app/
│       ├── lib/
│       │   ├── config/     # App configuration
│       │   ├── models/     # Data models
│       │   ├── services/   # API services
│       │   ├── screens/    # App screens
│       │   └── widgets/    # Reusable widgets
│       ├── assets/         # Images, fonts
│       └── pubspec.yaml
│
├── docker-compose.yml      # Docker setup
├── .env.example            # Environment variables
└── README.md               # This file
```

---

## 🔧 Technology Stack

### Backend
- **Framework:** Django 4.2
- **API:** Django REST Framework
- **Database:** PostgreSQL
- **Auth:** JWT (djangorestframework-simplejwt)
- **Payment:** Razorpay
- **PDF:** ReportLab
- **Image:** Pillow

### Frontend
- **Framework:** Flutter
- **State Management:** Provider
- **HTTP:** Dio
- **Storage:** SharedPreferences
- **Navigation:** GoRouter

### DevOps
- **Containerization:** Docker
- **Orchestration:** Docker Compose
- **Server:** Nginx + Gunicorn
- **Database:** PostgreSQL

---

## 📝 Environment Variables

Create `.env` file in backend:

```env
# Django
DEBUG=True
SECRET_KEY=your-secret-key-here
ALLOWED_HOSTS=localhost,127.0.0.1

# Database
DB_ENGINE=django.db.backends.postgresql
DB_NAME=mayso_db
DB_USER=postgres
DB_PASSWORD=your-password
DB_HOST=localhost
DB_PORT=5432

# Razorpay (Test Keys)
RAZORPAY_KEY_ID=rzp_test_xxxxxxxxxxxx
RAZORPAY_KEY_SECRET=xxxxxxxxxxxxxxxx

# Email (Optional)
EMAIL_BACKEND=django.core.mail.backends.console.EmailBackend

# CORS
CORS_ALLOWED_ORIGINS=http://localhost:3000,http://localhost:8100
```

---

## 🧪 Testing

### Run Tests
```bash
cd backend
python manage.py test
```

### Payment Testing
- Test Card: `4111 1111 1111 1111`
- Any future expiry date
- Any CVC
- OTP: Any 6 digits

---

## 🚀 Deployment

### Using Docker
```bash
docker-compose build
docker-compose up -d
```

### Production Checklist
- [ ] Change DEBUG to False
- [ ] Update SECRET_KEY
- [ ] Switch to production Razorpay keys
- [ ] Setup SSL certificate
- [ ] Configure static files
- [ ] Configure media files
- [ ] Setup database backups
- [ ] Setup logging
- [ ] Setup monitoring

---

## 📞 API Documentation

### Authentication
```bash
POST /api/v1/auth/register/
POST /api/v1/auth/login/
POST /api/v1/auth/refresh/
```

### Products
```bash
GET /api/v1/products/
GET /api/v1/products/{id}/
GET /api/v1/products/search/?q=shirt
GET /api/v1/categories/
```

### Shopping
```bash
GET /api/v1/cart/
POST /api/v1/cart/add/
POST /api/v1/cart/remove/
POST /api/v1/orders/
GET /api/v1/orders/
GET /api/v1/orders/{id}/
```

### Payments
```bash
POST /api/v1/payments/create-order/
POST /api/v1/payments/verify/
GET /api/v1/payments/history/
```

---

## 🐛 Common Issues

### Issue: `ModuleNotFoundError: No module named 'django'`
**Solution:**
```bash
source venv/bin/activate
pip install -r requirements.txt
```

### Issue: `CORS error`
**Solution:** Update CORS_ALLOWED_ORIGINS in settings.py

### Issue: `PostgreSQL connection error`
**Solution:** Check DB credentials in .env and PostgreSQL service status

### Issue: `Razorpay payment fails`
**Solution:**
- Verify test keys
- Amount must be in paise
- Check signature verification

---

## 📞 Support & Contact

- **Email:** hello@mayso.com
- **GitHub Issues:** [Report Issue](https://github.com/codewithmadhav/mayso-ecommerce/issues)
- **Documentation:** See docs/ folder

---

## 📄 License

MIT License - See LICENSE file

---

## 🙏 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

---

## 🎉 Get Started

**Ready to build MAYSO?**

1. Read [COMPLETE_ROADMAP_AND_QUICK_START.md](COMPLETE_ROADMAP_AND_QUICK_START.md)
2. Follow [PHASE_1_PLANNING.md](PHASE_1_PLANNING.md)
3. Start [PHASE_2_BACKEND_SETUP_PART_A.md](PHASE_2_BACKEND_SETUP_PART_A.md)

**Happy coding! 🚀**

---

*Last Updated: 2026-05-01*  
*Status: Phase 2 Implementation In Progress* 🔄
