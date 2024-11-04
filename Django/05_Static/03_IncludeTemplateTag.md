In Django, you can include HTML files using the `{% include %}` template tag. This is particularly useful for breaking down your templates into smaller, reusable components. Here’s how you can do it:

### Steps

1. **Create Your Template Files**: 
   Make sure you have the HTML file you want to include. For example, you might have a file named `header.html` in your templates directory.

2. **Use the `{% include %}` Tag**: 
   In your main template file, you can include the `header.html` file (or any other template) like this:

   ```django
   <!-- main_template.html -->
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>My Django Site</title>
   </head>
   <body>
       {% include 'header.html' %}
       
       <h1>Welcome to My Site</h1>
       <p>This is the main content area.</p>
       
       {% include 'footer.html' %}
   </body>
   </html>
   ```

3. **Ensure Template Directory is Set Up**: 
   Make sure your Django settings have the template directory configured correctly. In `settings.py`, you should have something like:

   ```python
   TEMPLATES = [
       {
           'BACKEND': 'django.template.backends.django.DjangoTemplates',
           'DIRS': [BASE_DIR,"templates"],
           'APP_DIRS': True,
           'OPTIONS': {
               'context_processors': [
                   'django.template.context_processors.debug',
                   'django.template.context_processors.request',
                   'django.contrib.auth.context_processors.auth',
                   'django.contrib.messages.context_processors.messages',
               ],
           },
       },
   ]
   ```

4. **File Paths**: 
   When using `{% include %}`, you can specify the relative path to the file. If `header.html` is in a subdirectory (like `partials`), you would include it like this:

   ```django
   {% include 'partials/header.html' %}
   ```

### Notes

- If the file does not exist, Django will raise a `TemplateDoesNotExist` error.
- You can also pass context to included templates. For example:

   ```django
   {% include 'header.html' with title="My Page Title" %}
   ```

   In `header.html`, you can then use `{{ title }}`.

Using `{% include %}` is a powerful way to maintain cleaner and more organized templates in Django. Let me know if you have any questions!
