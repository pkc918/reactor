# Skill: Go Backend Clean Architecture Project Structure Guide

## 1. Project Structure

```
.
├── api
│   ├── controller
│   ├── middleware
│   └── route
├── assets
├── bootstrap
├── cmd
├── domain
│   └── mocks
├── internal
├── db
│   └── mocks
├── repository
└── usecase
```

## 2. Folder Responsibilities

| Folder | Responsibility |
|---|---|
| cmd | Application entry point (main.go) |
| bootstrap | Initialize config, DB, app dependencies |
| api/route | Route registration |
| api/controller | Handle HTTP requests |
| api/middleware | Middleware (auth, logging, etc.) |
| domain | Core entities & interfaces |
| usecase | Business logic |
| repository | Data access implementation |
| db | Database layer |
| internal | utilities |
| domain/mocks | Domain mocks |
| db/mocks | Ddatabase mocks |

## 3. Naming Rules

### Controller
- {name}_controller.go

### Route
- {name}_route.go

### Usecase
- {name}_usecase.go

### Repository
- {name}_repository.go

### Domain
- {name}.go

### Middleware
- {name}_middleware.go

### Test
- *_test.go

## 4. API Example

### Flow
HTTP -> Route -> Middleware -> Controller -> Usecase -> Repository -> DB

### Request
```
curl GET http://localhost:8080/task
Authorization: Bearer token
```

### Response
```
[
  {"title": "Task 1"},
  {"title": "Task 2"}
]
```

## 5. Dev Steps

1. Define domain
2. Implement usecase
3. Implement repository
4. Add controller
5. Add route
6. Add middleware
7. Write tests
