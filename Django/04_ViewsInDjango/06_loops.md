In Django templates, you can use `{% for %}` to loop through lists or dictionaries. This is useful for displaying dynamic content like lists of items, user data, or any iterable collections. Here’s a straightforward example to demonstrate how to use loops in Django templates.

### Example Scenario

Let’s say you want to display a list of products with their names and prices.

### Step 1: Update the View

First, modify your `views.py` to pass a list of products to the template:

```python
from django.shortcuts import render

def home(request):
    products = [
        {'name': 'Product A', 'price': 25.00},
        {'name': 'Product B', 'price': 15.50},
        {'name': 'Product C', 'price': 35.75},
    ]
    
    data = {
        'title': 'Product List',
        'products': products,
    }
    return render(request, "index.html", data)
```

### Step 2: Create or Update the HTML Template

In your `index.html`, use the `{% for %}` loop to iterate through the products and display their names and prices:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>{{ title }}</title>
</head>
<body>
    <h1>{{ title }}</h1>

    <h2>Product List:</h2>
    <ul>
        {% for product in products %}
            <li>{{ product.name }} - ${{ product.price }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

### Explanation of the Template

1. **Using `{% for product in products %}`**: 
   - This initiates a loop over the `products` list. For each iteration, the current product is accessible via the variable `product`.

2. **Displaying Product Information**:
   - Within the loop, you can access the properties of each product (like `name` and `price`) using dot notation (e.g., `{{ product.name }}` and `{{ product.price }}`).

### Step 3: Run the Development Server

If your server isn’t running, start it with:

```bash
python manage.py runserver
```

### Step 4: Access the Home Page

Open your web browser and navigate to:

```
http://127.0.0.1:8000/
```

You should see a list of products displayed with their names and prices.

In Django templates, the primary way to iterate over collections is indeed with the `{% for %}` loop. However, Django templates also support several other control flow and filtering mechanisms. Here’s a brief overview:

### 1. `{% for %}` Loop
The main way to iterate through lists or dictionaries.

**Example**:
```django
{% for item in items %}
    <li>{{ item }}</li>
{% endfor %}
```

### 2. `{% if %}`, `{% elif %}`, and `{% else %}`
These statements allow for conditional logic, which can be combined with loops.

**Example**:
```django
{% for item in items %}
    {% if item.is_active %}
        <li>{{ item.name }}</li>
    {% else %}
        <li>{{ item.name }} (Inactive)</li>
    {% endif %}
{% endfor %}
```

### 3. `{% empty %}` Clause
Used with the `{% for %}` loop to handle empty lists.

**Example**:
```django
<ul>
    {% for item in items %}
        <li>{{ item }}</li>
    {% empty %}
        <li>No items found.</li>
    {% endfor %}
</ul>
```

### 4. `{% with %}`
Used to create a context variable for reuse, which can be useful in conjunction with loops.

**Example**:
```django
{% for item in items %}
    {% with item.price|floatformat:2 as formatted_price %}
        <li>{{ item.name }} - ${{ formatted_price }}</li>
    {% endwith %}
{% endfor %}
```

### 5. `{% include %}`
Allows you to include other templates, which can be useful for reusing code and combining loops.

**Example**:
```django
{% for item in items %}
    {% include 'item_template.html' with item=item %}
{% endfor %}
```

### 6. Template Filters
Django provides built-in filters that you can apply in your loops, such as `slice`, `dictsort`, and more.

**Example**:
```django
{% for item in items|slice:":5" %}
    <li>{{ item }}</li>
{% endfor %}
```

### Conclusion

While the `{% for %}` loop is the primary tool for iteration in Django templates, you also have a variety of other control flow and context management tools at your disposal. This allows for quite flexible and powerful template rendering. If you have specific use cases or questions, feel free to ask!
