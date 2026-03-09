# pydj_project

This is a foundational Django project configured with best practices for security and environment management. It serves as a robust starting point for building scalable and maintainable web applications.

## Features

*   **Framework**: [Django](https://www.djangoproject.com/)
*   **Database**: [PostgreSQL](https://www.postgresql.org/)
*   **Configuration**: Secure environment management using [python-decouple](https://pypi.org/project/python-decouple/), preventing secrets from being hardcoded.
*   **Dependency Management**: All dependencies are tracked in `requirements.txt`.

## Prerequisites

Before you begin, ensure you have the following installed on your system:
*   Python 3.12+
*   Pip (Python package installer)
*   PostgreSQL Server

## Local Development Setup

Follow these steps to get your development environment up and running.

**1. Clone the Repository**
```bash
git clone <your-repository-url>
cd pydj_project
```

**2. Create and Activate a Virtual Environment**

*   On macOS and Linux:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```
*   On Windows:
    ```bash
    python -m venv venv
    .\venv\Scripts\activate
    ```

**3. Install Dependencies**

Install all the required packages from `requirements.txt`.
```bash
pip install -r requirements.txt
```

**4. Set Up the Database**

Log in to PostgreSQL and create a database and a user for the project.
```sql
CREATE DATABASE pydj_db;
CREATE USER your_db_user WITH PASSWORD 'your_db_password';
GRANT ALL PRIVILEGES ON DATABASE pydj_db TO your_db_user;
```

**5. Configure Environment Variables**

Create a `.env` file in the project root directory. This file is ignored by Git and will hold your secret keys and local configuration.

Copy the following into your `.env` file and replace the placeholder values with your actual database credentials from the previous step.

```dotenv
# Django Settings
SECRET_KEY='django-insecure-bglx)mf6r^^zy#j7xa32e_#n_i$)+ns6pj7md*ux_lhd8j-0!8'
DEBUG=True

# PostgreSQL Database Credentials
DB_NAME=pydj_db
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=127.0.0.1
DB_PORT=5432
```

**6. Run Database Migrations**

Apply the database schema to your newly created database.
```bash
python manage.py migrate
```

**7. Run the Development Server**

You are now ready to run the application!
```bash
python manage.py runserver
```
The application will be available at `http://127.0.0.1:8000/`.
