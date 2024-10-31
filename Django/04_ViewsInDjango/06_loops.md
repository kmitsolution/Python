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

### Summary

You’ve successfully used loops in Django templates to iterate through a list and dynamically display content. This allows for flexible rendering of data based on context provided from your views. If you have more questions or need further examples, feel free to ask!
