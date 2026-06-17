# Opd-backend
# Happy Hospitals HMS - Backend API Engine

A robust, modular, and secure Hospital Operations & Outpatient Department (OPD) Management backend platform. This system handles patient onboarding, automated clinical queue token routing, secure pharmaceutical inventory checkout using database transactions, and real-time executive analytics.

## 🚀 Key Features

- **Decoupled Architecture:** Follows a strict separation of concerns where Patient records and Visit logs remain independent entities to allow multiple historical visits.
- **Automated Queue Management:** Live, daily calculations tracking active doctor assignments to auto-generate sequential patient token numbers.
- **Atomic Transaction Controls:** Uses row-level explicit locking (`select_for_update`) to safeguard pharmaceutical stock counts and guarantee billing invoice accuracy without race conditions.
- **Enterprise Security:** Secured sitewide by default using JSON Web Tokens (JWT) for role-based access controls.
- **Cross-Origin Framework Ready:** Pre-configured CORS policies optimized to seamlessly stream data with a standalone UI layer (e.g., Next.js running on port 3000).

---

## 🛠️ Technology Stack

- **Backend Framework:** Django 5.x & Django REST Framework (DRF)
- **Database Layer:** PostgreSQL
- **Authentication Protocol:** SimpleJWT (OAuth2 Bearer Tokens)
- **Environment Sandbox:** Python `venv`

---

## 📁 Repository Directory Structure

```text
opd-backend/
├── manage.py
├── core/
│   ├── settings.py      # Core connection string, CORS, and JWT parameters
│   └── urls.py          # Unified system global URL routing tree
├── apps/
│   ├── patients/        # Patient onboarding, vitals logging, & queue tracking
│   └── pharmacy/        # Medication inventory & atomic billing ledgers
└── venv/                # (Ignored) Isolated local Python runtime environments