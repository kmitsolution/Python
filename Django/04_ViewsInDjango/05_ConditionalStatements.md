In Django templates, you can use the `{% if %}` and `{% elif %}` statements to control the flow of your HTML based on certain conditions. This allows you to display different content depending on the context variables passed from your views.

### Example Scenario

Let's say you want to display a message based on the user's role, which could be "admin", "editor", or "viewer". Here's how you can implement this.

### Step 1: Update the View

First, update your `views.py` to pass a user role to the template:

```python
from django.shortcuts import render

def home(request):
    user_role = 'admin'  # This could be dynamically set based on actual user data
    data = {
        'title': 'Kmit Solutions Services',
        'msg': 'Welcome to KMIT Solutions Services',
        'user_role': user_role,
    }
    return render(request, "index.html", data)
```

### Step 2: Create or Update the HTML Template

In your `index.html` file, use the `{% if %}` and `{% elif %}` statements to display different messages based on the `user_role`:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>{{ title }}</title>
</head>
<body>
    <h1>{{ msg }}</h1>

    {% if user_role == 'admin' %}
        <p>Hello Admin! You have full access to the system.</p>
    {% elif user_role == 'editor' %}
        <p>Hello Editor! You can edit content but not manage users.</p>
    {% elif user_role == 'viewer' %}
        <p>Hello Viewer! You can only view content.</p>
    {% else %}
        <p>Hello Guest! Please log in to access more features.</p>
    {% endif %}

</body>
</html>
```

### Explanation of the Template

1. **Using `{% if %}`**: 
   - The template checks the value of `user_role`. If it matches "admin", it displays a message specific to admins.

2. **Using `{% elif %}`**: 
   - If `user_role` is not "admin", it checks if it’s "editor" and displays the corresponding message.

3. **Using `{% else %}`**: 
   - If none of the conditions match, it defaults to a guest message.

### Step 3: Run the Development Server

Make sure your server is running:

```bash
python manage.py runserver
```

### Step 4: Access the Home Page

Open your browser and navigate to:

```
http://127.0.0.1:8000/
```

You should see a personalized message based on the `user_role` you set in the view.

### Summary

You’ve successfully used conditional statements in Django templates to control the content displayed based on the context data. This feature allows for dynamic content rendering based on various conditions. If you have any further questions or need more examples, feel free to ask!
