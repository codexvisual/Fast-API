# # ⚡ FASTAPI COMPLETE MASTER GUIDE  
## 🚀 Beginner → Advanced → Production Ready Python API Framework

---

# 📖 What is FastAPI?

### 🇺🇸 English
FastAPI is a modern, high-performance Python web framework used to build APIs quickly with automatic documentation and async support.

### 🇧🇩 বাংলা
FastAPI হলো Python-এর একটি modern backend framework, যা দিয়ে খুব দ্রুত, high-performance এবং scalable API তৈরি করা যায়।

---

# 🌟 Why FastAPI?

- ⚡ Extremely Fast (High Performance)
- 🧠 Built-in type validation
- 📄 Auto API Docs (Swagger / Redoc)
- 🚀 Async support
- 🔐 Production ready
- 📦 Easy to scale microservices

---

# 🛠️ INSTALLATION

## Install FastAPI + Server

```bash
pip install fastapi uvicorn
```

---

## Check Python

```bash
python --version
```

---

# 🚀 FIRST FASTAPI APP

## main.py

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def home():
    return {"message": "Hello FastAPI"}
```

---

## Run Server

```bash
uvicorn main:app --reload
```

👉 Open:
```
http://127.0.0.1:8000
```

---

## API Docs

Swagger UI:
```
http://127.0.0.1:8000/docs
```

Redoc:
```
http://127.0.0.1:8000/redoc
```

---

# 📁 PROJECT STRUCTURE (PRO LEVEL)

```
app/
 ├── main.py
 ├── routes/
 ├── models/
 ├── schemas/
 ├── services/
 ├── database/
 ├── config/
 ├── utils/
```

---

# 🌐 ROUTES

## Basic GET

```python
@app.get("/hello")
def hello():
    return {"msg": "Hello"}
```

---

## POST API

```python
from fastapi import FastAPI

app = FastAPI()

@app.post("/create")
def create_item(data: dict):
    return data
```

---

## Path Parameter

```python
@app.get("/user/{user_id}")
def get_user(user_id: int):
    return {"user_id": user_id}
```

---

## Query Parameter

```python
@app.get("/search")
def search(q: str):
    return {"query": q}
```

---

# 📦 REQUEST BODY (Pydantic)

```python
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int

@app.post("/user")
def create_user(user: User):
    return user
```

---

# 🗄️ DATABASE (SQLAlchemy)

## Install

```bash
pip install sqlalchemy
```

---

## Database Setup

```python
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

DATABASE_URL = "sqlite:///./test.db"

engine = create_engine(DATABASE_URL)
SessionLocal = sessionmaker(bind=engine)
```

---

## Model Example

```python
from sqlalchemy import Column, Integer, String
from database import Base

class User(Base):
    __tablename__ = "users"

    id = Column(Integer, primary_key=True, index=True)
    name = Column(String)
```

---

# 🔐 AUTHENTICATION (JWT BASIC)

## Install

```bash
pip install python-jose passlib[bcrypt]
```

---

## Token Concept

```python
def create_token(data: dict):
    return "jwt-token"
```

---

# ⚡ ASYNC EXAMPLE

```python
@app.get("/async")
async def async_api():
    return {"message": "Async working"}
```

---

# 🌐 API FLOW

```
Client (React / Mobile App)
        ↓
FastAPI Server
        ↓
Pydantic Validation
        ↓
Service Layer
        ↓
Database
        ↓
JSON Response
```

---

# ⚙️ IMPORTANT COMMANDS

## Run Server

```bash
uvicorn main:app --reload
```

---

## Production Run

```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

---

## Install Packages

```bash
pip install fastapi uvicorn sqlalchemy
```

---

## Freeze Requirements

```bash
pip freeze > requirements.txt
```

---

## Install from file

```bash
pip install -r requirements.txt
```

---

# 🧰 BEST TOOLS

## 💻 IDE
- VS Code
- PyCharm

---

## 🔌 EXTENSIONS
- Python
- Pylance
- REST Client

---

## 🌐 TESTING TOOLS
- Postman
- Swagger UI
- Insomnia

---

# 🚀 PROJECT IDEAS

- REST API Backend
- AI Chatbot API
- E-commerce Backend
- ERP System
- Blog API
- SaaS Backend
- Authentication System

---

# 🟡 ADVANCED FASTAPI

## Dependency Injection

```python
from fastapi import Depends

def get_db():
    db = "connection"
    return db

@app.get("/db")
def read_db(db=Depends(get_db)):
    return db
```

---

## Middleware

```python
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_methods=["*"],
    allow_headers=["*"],
)
```

---

# 🔴 PRODUCTION DEPLOYMENT

## Install Gunicorn + Uvicorn

```bash
pip install gunicorn uvicorn
```

---

## Run Production Server

```bash
gunicorn -k uvicorn.workers.UvicornWorker main:app
```

---

## Deploy Options

- AWS EC2 ☁️
- DigitalOcean
- Render
- Railway
- VPS Linux Server

---

# ☁️ FASTAPI ARCHITECTURE

```
Frontend (React / Flutter)
        ↓
FastAPI Backend
        ↓
Service Layer
        ↓
Database (PostgreSQL / MongoDB)
        ↓
Cloud (AWS / Docker)
```

---

# 💡 PRO TIPS

✔ Always use Pydantic models  
✔ Use async for performance  
✔ Separate routes & services  
✔ Use dependency injection  
✔ Never hardcode secrets  
✔ Use environment variables  
✔ Use PostgreSQL in production  
✔ Dockerize your app  

---

# 👨‍💻 DEVELOPER

Md. Moklasur Rahman Rahat  
🚀 Full Stack Developer  
⚡ FastAPI & Python Backend Specialist  
💻 API & SaaS System Builder  

GitHub: codexvisual  

---

# ⭐ FINAL NOTE

FastAPI হলো modern Python backend development এর জন্য best choice — বিশেষ করে API, AI, SaaS এবং microservices এর জন্য।

---

⭐ If this FastAPI guide helps you, give it a star on GitHub
