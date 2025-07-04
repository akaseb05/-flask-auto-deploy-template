# flask-auto-deploy-template

A simple Flask web app with GitHub auto-deployment to PythonAnywhere, built as part of an SEO Developer Internship assignment. Includes database integration using SQLAlchemy and supports automatic updates via webhook.

---

# Flask Auto-Deploy Web App

This is a basic Flask web application with GitHub auto-deployment to PythonAnywhere.  
It was built as part of a technical assignment during my SEO Developer Internship, focusing on backend infrastructure, deployment automation, and Flask fundamentals.

---

## 🔧 Features

- Flask-powered web app  
- GitHub webhook-based auto-deployment using PythonAnywhere  
- SQLite database with SQLAlchemy ORM  
- `/update_server` route to pull new code on push  
- Ready for form submission and user data storage  

---
```
## 📂 File Structure
flask\_app/
├── app.py                # Main Flask app
├── requirements.txt      # Project dependencies
├── site.db               # SQLite database (auto-generated)
├── templates/
│   └── index.html        # HTML for homepage
└── static/
└── style.css         # CSS styling
```


## 🚀 How to Run Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   cd YOUR_REPO_NAME
```

2. **(Optional) Create a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Mac/Linux
   venv\Scripts\activate     # Windows
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Run the app**

   ```bash
   python app.py
   ```

5. **Visit in browser**

   * Go to: `http://127.0.0.1:5000`

---

## 🌐 Deployment to PythonAnywhere

1. Create an account on [https://www.pythonanywhere.com](https://www.pythonanywhere.com)

2. Clone your GitHub repo in the Bash console:

   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   cd YOUR_REPO_NAME
   ```

3. Install the requirements:

   ```bash
   pip3 install --user -r requirements.txt
   ```

4. Update the WSGI config:

   * Set project path and import your app from `app.py`

5. Set source code and working directory correctly under the **Web** tab

6. Add a webhook on GitHub:

   * Payload URL: `http://YOUR_USERNAME.pythonanywhere.com/update_server`
   * Content-Type: `application/json`

On push, PythonAnywhere will automatically pull the latest code.

---

## 🧪 Database Notes

* Database: `SQLite` (`site.db`)
* ORM: `SQLAlchemy`
* Tables are auto-created on app startup using:

  ```python
  with app.app_context():
      db.create_all()
  ```

To manually check the DB using the Flask shell:

```bash
export FLASK_APP=app.py
flask shell
>>> from app import User
>>> User.query.all()
```

---

## 📄 License

This project was created for educational purposes during an SEO Developer Internship and is open for use or modification.

```

---

✅ You can paste this straight into your `README.md` file. Let me know if you want to add badges, a project screenshot, or a "live preview" link.
```
