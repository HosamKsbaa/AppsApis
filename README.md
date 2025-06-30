# Police Officers Club API Documentation

[![Deploy Documentation](https://github.com/yourusername/police-club-api-docs/actions/workflows/deploy-docs.yml/badge.svg)](https://github.com/yourusername/police-club-api-docs/actions/workflows/deploy-docs.yml)
[![OpenAPI Spec](https://img.shields.io/badge/OpenAPI-3.0.3-green.svg)](./App1.json)

> **📖 [View Live API Documentation](https://yourusername.github.io/police-club-api-docs/)**

This repository contains the OpenAPI 3.0 specification and interactive documentation for the Police Officers Club API.

## 🚀 Quick Start

### View Documentation Online
- **Swagger UI**: [https://yourusername.github.io/police-club-api-docs/](https://yourusername.github.io/police-club-api-docs/)
- **Swagger Editor**: [Open in Editor](https://editor.swagger.io/?url=https://raw.githubusercontent.com/yourusername/police-club-api-docs/main/App1.json)
- **Raw OpenAPI Spec**: [App1.json](./App1.json)

### Run Documentation Locally

```bash
# Clone the repository
git clone https://github.com/yourusername/police-club-api-docs.git
cd police-club-api-docs

# Serve with Python (Python 3)
python -m http.server 8080

# Or with Node.js (if you have it installed)
npx serve .

# Open your browser to http://localhost:8080
```

## 📋 API Overview

The Police Officers Club API supports a comprehensive mobile application for Kuwait's Police Officers Club, providing:

### 🔐 Authentication
- Phone number-based authentication with OTP
- JWT token-based authorization
- Secure logout functionality

### 👥 Member Management
- Member registration with Civil ID verification
- Subscription management (monthly, quarterly, annual)
- Membership status tracking

### 🏖️ Chalet Services
- Browse available chalets with detailed information
- Check real-time availability and pricing
- Make reservations with integrated payment

### 🏊 Swimming Pool Reservations
- Pool availability checking
- Time slot booking system
- Dynamic pricing based on time and day

### 💳 Payment Processing
- KNET payment integration
- Invoice generation and management
- Payment status tracking

## 🛠️ API Details

### Base URL
```
https://api.policeclub.kw/v1
```

### Authentication
All endpoints (except authentication) require a Bearer token:

```http
Authorization: Bearer <jwt-token>
```

### Response Format
All responses follow a consistent JSON structure:

```json
{
  "success": true,
  "data": {},
  "message": "Operation successful"
}
```

### Error Handling
Standard HTTP status codes with detailed error messages:

```json
{
  "success": false,
  "error": {
    "code": "INVALID_PHONE",
    "message": "Phone number format is invalid",
    "details": "Kuwait phone numbers must be 8 digits starting with 5, 6, or 9"
  }
}
```

## 📚 API Endpoints Summary

| Category | Endpoint | Method | Description |
|----------|----------|---------|-------------|
| **Auth** | `/auth/phone-login` | POST | Send OTP to phone number |
| **Auth** | `/auth/verify-otp` | POST | Verify OTP and get tokens |
| **Auth** | `/auth/logout` | POST | Logout user |
| **Members** | `/members/register` | POST | Register new member |
| **Members** | `/members/subscription` | GET | Check subscription status |
| **Subscriptions** | `/subscriptions/create` | POST | Create new subscription |
| **Subscriptions** | `/subscriptions/options` | GET | Get available plans |
| **Chalets** | `/chalets` | GET | List all chalets |
| **Chalets** | `/chalets/{id}/slots` | GET | Get available time slots |
| **Chalets** | `/chalets/book` | POST | Book a chalet |
| **Pools** | `/swimming-pools` | GET | List swimming pools |
| **Pools** | `/swimming-pools/{id}/slots` | GET | Get available time slots |
| **Pools** | `/swimming-pools/book` | POST | Book swimming pool |
| **Payments** | `/payments/process` | POST | Process payment |
| **Payments** | `/payments/status/{id}` | GET | Check payment status |

## 🔧 Development

### Prerequisites
- OpenAPI 3.0.3 compatible tools
- Git for version control
- Modern web browser for documentation viewing

### Making Changes

1. **Fork and Clone**
   ```bash
   git clone https://github.com/yourusername/police-club-api-docs.git
   cd police-club-api-docs
   ```

2. **Edit OpenAPI Spec**
   - Modify `App1.json` with your changes
   - Validate using [Swagger Editor](https://editor.swagger.io/)

3. **Test Locally**
   ```bash
   # Validate the OpenAPI spec
   npx @stoplight/spectral-cli lint App1.json
   
   # Serve documentation locally
   python -m http.server 8080
   ```

4. **Commit and Push**
   ```bash
   git add .
   git commit -m "Update API documentation"
   git push origin main
   ```

### Validation

The OpenAPI specification is automatically validated on each commit using Spectral:

```bash
# Install Spectral globally
npm install -g @stoplight/spectral-cli

# Validate the spec
spectral lint App1.json --ruleset spectral:oas
```

## 🚀 Deployment

Documentation is automatically deployed to GitHub Pages when changes are pushed to the main branch.

### Manual Deployment

If you need to deploy manually:

```bash
# Build documentation
mkdir -p dist
cp App1.json dist/
cp index.html dist/

# Deploy to your hosting service
```

## 📱 Mobile App Integration

This API is designed for the Police Officers Club mobile application built with Flutter. Key integration points:

- **Authentication Flow**: Phone → OTP → JWT tokens
- **Offline Support**: Cache responses for better UX
- **Payment Integration**: KNET payment gateway
- **Localization**: Supports Arabic and English content

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Guidelines

- Follow OpenAPI 3.0.3 specification
- Include examples for all endpoints
- Document all error responses
- Update this README if needed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Support

- **Website**: [https://policeclub.kw](https://policeclub.kw)
- **Email**: support@policeclub.kw
- **Issues**: [GitHub Issues](https://github.com/yourusername/police-club-api-docs/issues)

## 🏷️ Version History

- **v1.0.0** - Initial API specification
  - Authentication system
  - Member management
  - Chalet and pool booking
  - Payment processing

---

**Built with ❤️ for Kuwait's Police Officers Club**
