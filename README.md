# Property Portfolio Manager

Comprehensive application consisting of a Python-based backend and a React/TypeScript frontend.

## 🛠 Project Structure

- **backend/**: FastAPI application with SQLAlchemy models, authentication, services, and database migrations.
  - `app/`: main application code (API routes, services, models, schemas).
  - `core/`: configuration, database connection and settings.
  - `auth/`: authentication service.
  - `models/` & `schemas/`: ORM and Pydantic definitions.
  - `services/`: business logic for portfolios, properties, email, files, and calculations.
  - `migrations/`: Alembic configuration and versioned migration scripts.
  - `requirements.txt`, `Dockerfile`, `alembic.ini`, etc.

- **frontend/**: React + TypeScript SPA using Tailwind CSS.
  - `src/`: components, pages, stores, utilities organized by feature (auth, portfolios, properties).
  - `public/` and build configuration files.

## 🚀 Getting Started

### Backend

1. **Create a virtual environment** and install dependencies:
   ```powershell
   cd backend
   python -m venv venv
   .\\venv\\Scripts\\Activate.ps1
   pip install -r requirements.txt
   ```
2. **Configure environment variables** (see `app/core/settings.py` for required keys).
3. **Run database migrations**:
   ```powershell
   alembic upgrade head
   ```
4. **Start the server**:
   ```powershell
   uvicorn app.main:app --reload
   ```

### Frontend

1. Install Node dependencies:
   ```powershell
   cd ..\\frontend
   npm install
   ```
2. Configure `public/config.js` or environment as needed.
3. Start development server:
   ```powershell
   npm run dev
   ```
4. Visit `http://localhost:3000` (or the port configured) in the browser.

## 📦 Deployment

- Backend contains Dockerfile and `docker-compose.yml` for containerized deployment.
- `railway.toml` present for Railway hosting configuration.

## 🧪 Testing

- Backend tests live under `backend/app/tests/` (pytest).
- Run with:
  ```powershell
  cd backend
  pytest
  ```

## 📄 Additional Notes

- **Authentication** is JWT-based implemented in `backend/app/api/auth.py` and `auth/service.py`.
- **Portfolio management** supports folders, assets, default flags, icons, and subscription tiers.
- **Property and calculation services** perform financial metrics and mortgage computations.

## 🤝 Contributing

Feel free to open issues or PRs. Ensure tests pass and linting is clean.
