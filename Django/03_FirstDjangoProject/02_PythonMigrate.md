Let’s walk through the steps you mentioned for configuring your Django project and working with the development server, including setting up templates, running migrations, and installing an SQL database browser.

### Step 4: Configure Template Directory in `settings.py`

To set up the templates directory, you will need to modify the `settings.py` file:

1. Open `mysite/mysite/settings.py`.
2. Locate the `TEMPLATES` section and modify it to include the templates directory. You can update the `DIRS` key as follows:

```python
import os

BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))

TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates'), ''],  # Add the template directory here
        ...
    },
]
```

This configuration tells Django to look for templates in the `templates` directory you created earlier.

### Step 5: Run Migrations

After configuring your project, you need to apply the initial migrations to set up your database schema:

1. In your terminal, make sure you are in the project directory (where `manage.py` is located).
2. Run the following command:

```bash
python manage.py migrate
```

This command applies the migrations, setting up the necessary database tables for Django's built-in apps like authentication and sessions.

### Step 6: Install SQL Database Browser

To interact with your database visually, you can use an SQL database browser. One popular option is **DB Browser for SQLite**, which works well with Django’s default SQLite database.

1. **Download DB Browser for SQLite**:
   - Go to the [official website](https://sqlitebrowser.org/).
   - Download the version compatible with your operating system (Windows, macOS, Linux).

2. **Install the Application**:
   Follow the installation instructions for your specific operating system.

3. **Open Your SQLite Database**:
   After installing, you can open the SQLite database that Django created. By default, this database file is located at:

   ```
   mysite/db.sqlite3
   ```

   You can open this file in DB Browser for SQLite to view and manage your data.

### Summary

Now you have:

1. Configured the template directory in your Django project.
2. Applied database migrations to set up the necessary tables.
3. Installed an SQL database browser to manage your SQLite database.

If you have any further questions or need additional assistance, feel free to ask!
