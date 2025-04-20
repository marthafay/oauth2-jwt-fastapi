# oauth2-jwt-fastapi

A minimal OAuth2-compatible FastAPI gateway that verifies Google ID tokens (Authorization Code Flow) and issues its own JWTs for access control.

Built for personal AI projects (e.g. GPT agents) requiring secure, token-based access to protected routes.

---

## 🔒 Features

- OAuth2 Authorization Code Flow (Google)
- Verifies Google ID tokens
- Issues signed JWTs using your secret key
- Protects routes via OAuth2 Bearer token
- Fully local testable with Swagger UI

---

## 🚀 Quickstart

### 1. Clone repository
```bash
git clone https://github.com/yourusername/oauth2-jwt-fastapi.git
cd oauth2-jwt-fastapi
```

### 2. Setup virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 3. Configure environment variables
Copy the template and fill in your own values:
```bash
cp .env.template .env
```

### 4. Run the app
```bash
uvicorn app.main:app --reload
```

### 5. Test locally
Open: [http://localhost:8000/docs](http://localhost:8000/docs)

Use the “Authorize” button to provide a valid token and access protected routes.

---

## 🔁 Auth Flow Summary

1. Frontend logs in via Google → gets ID Token
2. Sends ID Token to `/token` endpoint
3. FastAPI verifies the ID Token, returns signed JWT
4. JWT is used to access `/protected` endpoint

---

## 📄 .env.template
```env
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
JWT_SECRET_KEY=
REDIRECT_URI=http://localhost:8000/auth/callback
```

---

## ✍️ Author
Built & documented by [Your Name], inspired by ChatGPT-based architecture design.

---

## 📜 License
MIT
