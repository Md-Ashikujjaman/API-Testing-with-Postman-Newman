
# Expand Notes API Testing with Postman & Newman

This project demonstrates automated API testing for the [Expand Notes API](https://practice.expandtesting.com/notes/api) using Postman and Newman. It includes a complete collection of test cases covering common CRUD operations, authentication, and health check of the API.

---

## 🔧 Features

- ✅ Health check endpoint verification  
- 📝 Full CRUD testing for notes (Create, Read, Update, Delete)  
- 🔐 Authentication testing (Token-based login)  
- 🔁 Environment-based configuration  
- 🧪 Pre-request scripts and test scripts  
- 📊 Newman integration for CLI execution and HTML report generation  

---

## 📄 API Documentation

**Base URL:** `https://practice.expandtesting.com/notes/api`

You can view the live documentation or import the collection into Postman for testing.

---

## 🧰 Technology Used

- Postman  
- Newman  
- Newman Reporter HTML Extra  

---

## 📝 Prerequisites

- [Node.js](https://nodejs.org/)
- Newman: `npm install -g newman`
- Newman HTML Extra Reporter: `npm install -g newman-reporter-htmlextra`

---

## 🧪 Installation & Setup

### 🔽 Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/expand-notes-api-postman.git
cd expand-notes-api-postman
```

### 📥 Step 2: Import into Postman

#### 📁 Import Collection:
1. Open Postman  
2. Click **Import** → Choose the `Expand_Notes_API.postman_collection.json`

#### 🌍 Import Environment:
1. Click the gear icon (⚙️) in the top-right corner  
2. Click **Import** → Select `Expand_Notes_Env.postman_environment.json`

---

## 🚀 Running the Tests

### ▶️ Using Newman (Command Line):

#### Basic Command:
```bash
newman run Expand_Notes_API.postman_collection.json -e Expand_Notes_Env.postman_environment.json
```

#### With HTML Report:
```bash
newman run Expand_Notes_API.postman_collection.json -e Expand_Notes_Env.postman_environment.json -r cli,htmlextra
```

---

## ✅ Test Case Scenarios

### 1. Health Check
- **URL:** `GET /health-check`  
- **Validation:** Server status 200 OK

---

### 2. User Authentication (Login)
- **URL:** `POST /users/login`  
- **Body:**  
  ```json
  {
    "email": "test@expandtesting.com",
    "password": "test123"
  }
  ```
- **Response:** JWT token

---

### 3. Create Note
- **URL:** `POST /notes`  
- **Body:**  
  ```json
  {
    "title": "API Testing Note",
    "content": "This is a note created using Postman."
  }
  ```
- **Validation:** Status 201 Created

---

### 4. Get All Notes
- **URL:** `GET /notes`  
- **Validation:** Status 200 OK, returns array of notes

---

### 5. Get Note by ID
- **URL:** `GET /notes/:id`  
- **Validation:** Status 200 OK, valid note object

---

### 6. Update Note
- **URL:** `PUT /notes/:id`  
- **Body:**  
  ```json
  {
    "title": "Updated Title",
    "content": "Updated note content."
  }
  ```
- **Validation:** Status 200 OK

---

### 7. Delete Note
- **URL:** `DELETE /notes/:id`  
- **Validation:** Status 204 No Content

---

## 📊 Newman HTML Report Output

After running with `htmlextra`, an HTML report is generated in your terminal or saved (if specified with `--reporter-htmlextra-export`).

---

## 🧩 Troubleshooting

### 🚫 Error: “You are not authorized to send a request through the cloud agent”
**Solution:**  
- Use the Postman **Desktop App**  
- Or install and run **Postman Agent**  
- Switch from **Cloud Agent** to **Local Agent** in the top-right corner

---

## 🙌 Credits

Tested with ❤️ by [Md. Ashikujjaman](https://www.linkedin.com/in/mdashikujjaman/)
Mentor: [Md. Ebrahim Hossain](https://www.linkedin.com/in/mdebrahimhossain/)
API: [https://practice.expandtesting.com/notes/api](https://practice.expandtesting.com/notes/api)

---

## 📁 License

This project is for educational purposes only.
