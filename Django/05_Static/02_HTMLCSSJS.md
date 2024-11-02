# Note (Alternate way)
In your templates, use the static template tag to build the URL for the given relative path using the configured staticfiles STORAGES alias.

```html
{% load static %}
<img src="{% static 'my_app/example.jpg' %}" alt="My image">
```
