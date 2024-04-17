# FastAPI + Streamlit
This project showcases the use of `FastAPI` and `Streamlit` for web application development projects. 

## Directory structure
---
```
.
├── README.md
├── docker-compose.yml
├── docker
│   ├── fastapi
│   │   ├── Dockerfile
│   │   └── requirements.txt
│   └── streamlit
│       ├── Dockerfile
│       └── requirements.txt
├── app-backend
│   ├── src
│   │   ├── __init__.py
│   │   ├── main.py
│   │   ├── cruds
│   │   │   ├── __init__.py
│   │   │   ├── books.py
│   │   │   ├── users.py
│   │   │   └── domains
│   │   │       ├── __init__.py
│   │   │       └── search.py
│   │   ├── database
│   │   │   ├── __init__.py
│   │   │   ├── db.py
│   │   │   └── migrate_db.py
│   │   ├── models
│   │   │   ├── __init__.py
│   │   │   ├── book.py
│   │   │   └── user.py
│   │   ├── routers
│   │   │   ├── __init__.py
│   │   │   ├── books.py
│   │   │   └── users.py
│   │   ├── schemas
│   │   │   ├── __init__.py
│   │   │   ├── book.py
│   │   │   └── user.py
│   │   ├── services
│   │   │   ├── __init__.py
│   │   │   └── non_crud_func.py
│   │   └── utils
│   │       ├── __init__.py
│   │       └── logger.py
│   └── tests
│       ├── __init__.py
│       └── test_sample.txt
└── app-front
    ├── __init__.py
    └── app.py

```

## How to use
---
Clone this repo and run the below docker command:

`To Start Application`:
```docker
docker-compose up --build
```
and navigate to http://localhost:8080/ .

`To Stop Application`:
```docker
docker-compose down
```
