# 🚀 HRMS -- Human Resource Management System

A full-stack Human Resource Management System built with modern scalable
architecture.

## 🏗️ Tech Stack

### Frontend

-   Next.js
-   React

### Backend

-   FastAPI
-   SQLAlchemy 2.0
-   Alembic (Database Migration)
-   Pydantic v2
-   JWT Authentication
-   Uvicorn

### Database

-   PostgreSQL
-   Psycopg2

### AI & Integrations

-   OpenAI
-   Google Generative AI
-   Supabase
-   SMTP (aiosmtplib)

------------------------------------------------------------------------

# 📂 Project Structure

hrms/ │ ├── frontend/ \# Next.js Frontend ├── backend/ \# FastAPI
Backend │ ├── main.py │ ├── models/ │ ├── schemas/ │ ├── routers/ │ ├──
services/ │ ├── alembic/ │ ├── requirements.txt │ └── .env └── README.md

------------------------------------------------------------------------

# ⚙️ Backend Setup (FastAPI)

## Prerequisites

-   Python 3.10.12
-   PostgreSQL 14+
-   pip

## 1️⃣ Clone Repository

git clone https://github.com/naiyerazm/hrms.git cd hrms/backend

## 2️⃣ Create Virtual Environment

python3.10 -m venv venv

Activate:

Windows: venv`\Scripts`{=tex}`\activate`{=tex}

Mac/Linux: source venv/bin/activate

## 3️⃣ Install Dependencies

pip install -r requirements.txt

## 4️⃣ Setup Environment Variables (.env)

DATABASE_URL=postgresql://username:password@localhost:5432/hrms_db
SECRET_KEY=your_secret_key ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

SMTP_HOST=smtp.gmail.com SMTP_PORT=587 SMTP_USER=your_email
SMTP_PASSWORD=your_password

OPENAI_API_KEY=your_openai_key GOOGLE_API_KEY=your_google_key

## 5️⃣ Create Database

CREATE DATABASE hrms_db;

## 6️⃣ Run Migrations

alembic upgrade head

## 7️⃣ Run Backend

Development: uvicorn main:app --reload

Production: uvicorn main:app --host 0.0.0.0 --port 8000

Swagger Docs: http://127.0.0.1:8000/docs

------------------------------------------------------------------------

# 💻 Frontend Setup (Next.js)

cd ../frontend npm install

Create .env.local: NEXT_PUBLIC_API_URL=http://127.0.0.1:8000

Run: npm run dev

Frontend runs at: http://localhost:3000

------------------------------------------------------------------------

# 🐳 Docker (Optional)

FROM python:3.10-slim

WORKDIR /app COPY requirements.txt . RUN pip install --no-cache-dir -r
requirements.txt COPY . . CMD \["uvicorn", "main:app", "--host",
"0.0.0.0", "--port", "8000"\]

------------------------------------------------------------------------

# 📊 Requirements Summary

-   Python 3.10.12
-   Node.js 18+
-   PostgreSQL 14+

------------------------------------------------------------------------

# 📄 License

MIT License
