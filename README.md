# Job Description Analyser

A smart application that enables recruiters to refine job descriptions for clarity, inclusivity, and industry alignment. The application dynamically enhances JDs by analyzing structure, language biases, readability, and SEO performance.

**Live**: [jdbuilder.vercel.app](https://jdbuilder.vercel.app)

---

## Why This Exists

- Job descriptions are often written with unconscious bias, unclear structure, and poor SEO
- Recruiters spend hours manually reviewing and rewriting JDs
- No lightweight tool existed for Atlan-specific JD standards and branding
- Readability and inclusivity analysis is typically manual and inconsistent

## Features

- Multiple input methods (text, file upload, structured form)
- Dynamic JD structuring & enhancement
- Gender-neutral & bias-free language optimization
- Readability & SEO analysis
- Interactive enhancement with user confirmation
- Atlan-aligned design & branding

## Tech Stack

- **Frontend**: React + TypeScript + Vite + Material UI
- **Backend**: Python FastAPI
- **Database**: PostgreSQL (Supabase)
- **AI/ML**: HuggingFace Inference API (facebook/bart-large-cnn)
- **Auth**: JWT
- **Hosting**: Vercel (frontend) + Render/Railway (backend)

## Quick Start

### Backend

```bash
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env  # Edit with your credentials
uvicorn app.main:app --reload
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on `http://localhost:3000`, backend on `http://localhost:8000`.

## Environment Variables

Create a `.env` file in the project root:

```
DATABASE_URL=postgresql://user:password@localhost:5432/jd_analyzer
HUGGINGFACE_API_KEY=your_huggingface_api_key
JWT_SECRET=your_jwt_secret
JWT_ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
ALLOWED_ORIGINS=http://localhost:3000
```

The frontend uses `VITE_API_BASE_URL` in `frontend/.env.production` to point to the backend API.

## API Documentation

Once the backend is running, visit:
- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

## Deployment

| Component | Platform | URL |
|-----------|----------|-----|
| Frontend  | Vercel   | [jdbuilder.vercel.app](https://jdbuilder.vercel.app) |
| Backend   | Render   | `jd-analyzer-backend.onrender.com/api` |

## License

MIT
