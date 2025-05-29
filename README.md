
# Flask Auth0 Demo App

This is a simple Flask web application that demonstrates user authentication with **Auth0**. It is based on the [Auth0 Python Flask Quickstart Tutorial](https://auth0.com/docs/quickstart/webapp/python#configure-auth0) with added functionality for a protected route accessible only to authenticated users.

---

## 🧩 Features

- Login and Logout with Auth0
- Session-based user authentication
- Protected route (`/protected`) that requires login
- Display user profile data after login

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yvanniyonzima-ac/cst8919-lab1-auth-python.git
cd cst8919-lab1-auth-python
```

---

### 2. Set Up a Virtual Environment (Optional but Recommended)

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

---

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

If you don't have a `requirements.txt`, here are the main dependencies:

```bash
pip install flask authlib python-dotenv
```

---

## 🔐 Auth0 Configuration

Follow the [Auth0 Quickstart Tutorial](https://auth0.com/docs/quickstart/webapp/python#configure-auth0) up to the "Run the sample application" section.

1. Go to [Auth0 Dashboard](https://manage.auth0.com/).
2. Create an Application of type **Regular Web Application**.
3. In **Application Settings**, add the following:

   - **Allowed Callback URLs**:  
     ```
     http://127.0.0.1:3000/callback
     http://localhost:3000/callback
     ```
   - **Allowed Logout URLs**:  
     ```
     http://127.0.0.1:3000
     http://localhost:3000
     ```
   - **Allowed Web Origins**:  
     ```
     http://127.0.0.1:3000
     http://localhost:3000
     ```

---

## ⚙️ Environment Variables

Create a `.env` file in the root of your project and add the following:

```env
AUTH0_CLIENT_ID=your_auth0_client_id
AUTH0_CLIENT_SECRET=your_auth0_client_secret
AUTH0_DOMAIN=your-auth0-domain.auth0.com
APP_SECRET_KEY=some-random-string
```

Replace the values with your actual Auth0 application settings.

---

## 🏃 Running the App

Once everything is configured:

```bash
python server.py
```

Then visit `http://localhost:3000` in your browser.

---

## 🔒 Protected Route

The `/protected` route is only accessible to authenticated users.

- If a user visits `/protected` while not logged in, they will be redirected to the login page.
- After logging in, they can view the protected content.

---

## 📂 Project Structure

```
.
├── server.py
├── .env
├── requirements.txt
├── templates/
│   ├── home.html
│   └── protected.html
└── README.md
```

---

## 📚 References

- [Auth0 Python Quickstart](https://auth0.com/docs/quickstart/webapp/python)
- [Authlib Documentation](https://docs.authlib.org/)

---

## 🧑‍💻 Author

This project was built as part of an authentication lab based on Auth0's tutorial.
