
# 📊 Internship Backend Project: Unlisted Stock App

## 🎯 Project Goal

Build a backend API to:
- List all stocks
- View stock details
- Display all transactions
- Add a new stock
- Edit the price of a stock

---

## 🧱 Phase 1: Project Setup & Boilerplate

- [x] **Initialize project with `npm init`**  
  Set up the Node.js project structure. This creates a `package.json` to manage dependencies and scripts.

- [x] **Install Express and Nodemon**  
  Install Express for server creation and Nodemon for hot reloading during development.

- [x] **Set up basic Express server (`app.js`)**  
  Create a minimal Express server that listens on `localhost:5000` and responds to a test route.

- [ ] **Install and configure `dotenv`**  
  Use `dotenv` to manage environment variables securely (like MongoDB URI, port).

- [ ] **Connect MongoDB using Mongoose**  
  Use Mongoose to connect your app to MongoDB and handle schemas/models.

---

## 📦 Phase 2: Create Core MongoDB Models

- [ ] **Create `Product` model**  
  Schema for stock/company information like name, ISIN, sector, description, directors, etc.

- [ ] **Create `Price` model**  
  Schema for storing latest or historical stock prices related to a product.

- [ ] **Create `Transaction` model**  
  Schema for recording buy/sell transactions including type, quantity, price, and timestamp.

---

## 📡 Phase 3: Build REST APIs

- [ ] **`GET /stocks` - List all stocks**  
  Fetch all stocks from the database and return key details like name, ISIN, and category.

- [ ] **`GET /stocks/:id` - Stock details (product + price)**  
  Return detailed information for one stock including price, description, and financials.

- [ ] **`POST /stocks` - Add new stock**  
  Add a new entry to the `Product` collection with basic details provided in the request.

- [ ] **`PUT /stocks/:id/price` - Update stock price**  
  Update the price entry for a given stock. This could either update the latest or insert a new one.

- [ ] **`GET /transactions` - List all transactions**  
  Fetch all transaction records across products. Useful for auditing or user history.

- [ ] **`POST /transactions` - Create a transaction**  
  Create a new buy/sell record with product reference, type, quantity, and price.

---

## 🧪 Phase 4: Testing & Validation

- [ ] **Create Postman Collection for API testing**  
  Save API endpoints in a Postman collection to easily test and share with teammates.

- [ ] **Add basic input validation for routes**  
  Ensure required fields are present (e.g., name for product, price must be a number).

- [ ] **Add error handling (try/catch + custom messages)**  
  Send proper HTTP status codes and error messages for better debugging and frontend usage.

---

## 🧰 Phase 5: Project Polish (Optional but Recommended)

- [ ] **Add `morgan` for logging requests**  
  Log every request in development for easy tracing and debugging.

- [ ] **Create `.gitignore` for `node_modules`, `.env`**  
  Prevent unnecessary files from being committed to Git.

- [ ] **Use `.env` for environment configs like `MONGO_URI`**  
  Securely store connection strings and sensitive info outside of codebase.

- [ ] **Use clean MVC structure: `models/`, `controllers/`, `routes/`**  
  Follow best practices in code organization for maintainability and scalability.

---

## 🧗 Phase 6: Feedback & Review

- [ ] **Push project to GitHub**  
  Upload the code to a remote repository for version control and review.

- [ ] **Share with Prachet for review**  
  Ask for feedback on structure, code quality, and logic implementation.

- [ ] **Implement review feedback**  
  Make improvements based on the suggestions to align with team standards.

- [ ] **Finalize and document**  
  Clean up the code, add final comments, and ensure everything is production-ready.

---

## ✅ Tech Stack

- Node.js
- Express.js
- MongoDB + Mongoose
- Postman (for testing)
- dotenv, morgan (utils)

---

## 🧠 Pro Tips

- Commit often with meaningful messages
- Keep one route working before starting the next
- Log everything during dev, silence in production
- Ask for feedback early to improve
