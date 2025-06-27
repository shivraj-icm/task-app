# 📘 Stock Management App - Backend Development Plan

## 🔧 Project Overview

This project is a backend-driven stock management application. It allows users (or the future frontend) to manage unlisted equity stocks, view stock details, add new stocks, update their prices, and view transaction history. The backend is built using **Node.js, Express.js, and MongoDB**, and tested using **Postman** for now.

The frontend will be developed later. For now, we focus on building a clean, well-structured, and production-grade backend.

---

## 📁 Project Structure

```
/stock-management-app
├── /backend               # Express.js API and all server-side code
│   ├── /models            # MongoDB models for stocks, prices, transactions
│   ├── /controllers       # Handle incoming API logic
│   ├── /routes            # Define API endpoints
│   ├── /services          # Business logic layer
│   ├── /config            # DB connection, environment setup
│   ├── server.js          # Main server file
│   └── package.json       # Backend dependencies
├── /frontend              # Placeholder for future React frontend
│   └── README.md          # Note for frontend devs
├── /docs                  # API documentation and Postman collection
│   ├── api.postman_collection.json
│   └── api-spec.md
├── /scripts               # Scripts like DB seeders, utilities
├── .gitignore             # Ignore node_modules, .env etc.
├── .env.example           # Example environment file
├── README.md              # Project overview and setup guide
```

---

## 🔰 Phase 1: Project Initialization (Estimated: 1 Day)

### ✅ Objectives:
- Initialize project directory and Git repository.
- Setup environment variables, basic configuration, and linting.
- Create initial folder structure for backend and placeholder for frontend.

### 📝 Steps:
1. **Create Folder Structure:**
   ```bash
   mkdir stock-management-app && cd stock-management-app
   mkdir backend frontend docs scripts
   cd backend && npm init -y
   ```

2. **Initialize Git and Create GitHub Repo:**
   ```bash
   git init
   echo "/node_modules" >> .gitignore
   echo ".env" >> .gitignore
   ```

3. **Add .env Example File:**
   ```env
   PORT=5000
   MONGO_URI=mongodb://localhost:27017/stockapp
   ```

4. **Add Linter and Formatter:**
   ```bash
   npm install --save-dev eslint prettier
   npx eslint --init
   ```

5. **Set Up CI/CD (Optional for Now):**
   Add `.github/workflows/ci.yml` to run lint on PRs.

---

## 🧱 Phase 2: Backend – API & Database Models (Estimated: 1–2 Days)

### ✅ Objectives:
- Build backend server using Express.js
- Create models for stock, prices, and transactions using Mongoose
- Add controllers and routes to perform CRUD operations

### 📝 Models:
- **UnlistedEquityProduct:**
  - Fields: name, symbol, industry, description, isActive

- **UnlistedEquityPrice:**
  - Fields: stockId (ref to UnlistedEquityProduct), price, date

- **UnlistedEquityTransaction:**
  - Fields: stockId (ref), type (buy/sell), quantity, price, date

### 📝 API Routes:
- `GET    /stocks` → List all stocks
- `GET    /stocks/:id` → Get stock details
- `POST   /stocks` → Add a new stock
- `PUT    /stocks/:id` → Update stock details (like price)
- `GET    /transactions/:stockId` → List transactions for a stock

### 🧠 Structure Best Practices:
- Keep controllers small; delegate to services for logic.
- Use `express-validator` or `joi` for input validation.
- Group API routes by domain inside `/routes` folder.

---

## 🧪 Phase 3: API Testing with Postman (Estimated: 0.5–1 Day)

### ✅ Objectives:
- Test API endpoints manually using Postman
- Handle edge cases and check validations

### 📝 Steps:
1. Create a new **Postman collection**
2. Add all API endpoints:
   - Include example payloads
   - Add tests for:
     - Valid input
     - Missing fields
     - Invalid ID format
3. Export Postman Collection to `/docs/api.postman_collection.json`

---

## 🧩 Phase 4: Frontend Placeholder (For Later)

### ✅ Objectives:
- Reserve space for frontend work
- Leave a README for the future frontend developer

### 📁 `/frontend/README.md`:
```md
# Frontend Placeholder

This folder is reserved for the future React frontend of the Stock Management App.
You can use Vite or CRA to set up the frontend here when needed.
```

---

## 📑 Phase 5: Documentation (Estimated: 0.5 Day)

### ✅ Objectives:
- Document all routes, environment setup, and usage instructions

### 📝 Files:
- **README.md**
  - Project intro
  - How to run the app
  - How to connect to DB
  - API route overview

- **docs/api-spec.md**
  - Describe each endpoint
  - Sample requests/responses
  - Error formats

- **.env.example**
  - Add placeholders for required env variables

---

## 🚀 Phase 6: Deployment (Optional / Future)

### ✅ Objectives:
- Prepare the backend for deployment

### 📝 Steps:
- Create `Dockerfile` and `docker-compose.yml`
- Add `start` and `start:dev` scripts to `package.json`
- Deploy on Railway / Render or host manually

---

## 🧩 Final Notes
- Follow semantic commits: `feat:`, `fix:`, `chore:`, etc.
- Always keep `.env` out of Git.
- Document what you build as you go.
- Ask for code review if working with team.
- Keep frontend minimal or skip it until backend is complete.

---

## 📌 Summary Table

| Phase | Name | Time Estimate | Description |
|-------|------|----------------|-------------|
| 1     | Project Initialization | 1 Day | Setup repo, folder structure, config, linting |
| 2     | Backend API & Models  | 1–2 Days | Build Express server, Mongo models, routes |
| 3     | API Testing with Postman | 0.5–1 Day | Test all endpoints with valid/invalid data |
| 4     | Frontend Placeholder | 0.1 Day | Reserve space for future UI |
| 5     | Documentation | 0.5 Day | Write README, env guide, API spec |
| 6     | Deployment | Optional | Prepare for production deployment |

---

> ✅ You are now ready to start building your backend like a pro. Let me know if you want auto-generated starter files, like model templates or `server.js` boilerplate!

