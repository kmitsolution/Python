# HTML Project in Django

Consider below is the directory sturcture of Html project which you need to incoprorate in Django Project

my-simple-project/
│
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
└── images/
    └── sample-image.jpg


Copy the files as below in project

my_django_project/
│
├── myapp/
│   
│   ├── static/
│   │   ├── css/
│   │   │   └── styles.css
│   │   ├── js/
│   │   │   └── script.js
│   │   └── images/
│   │       ├── sample-image.jpg
│   │       └── sample-image2.jpg
│   ├── templates/
│   │      └── index.html

### index.html (use static/ to refer images and js files)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Project</title>
    <link rel="stylesheet" href="static/css/styles.css">
</head>
<body>
    <div class="container">
        <h1>Welcome to My Simple Project</h1>
        <img id="image" src="static/images/sample-image.jpg" alt="Sample Image" width=500 height=500>
        <button id="changeImageButton">Change Image</button>
    </div>
    <script src="static/js/script.js"></script>
</body>
</html>

```
### css file
```css
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.container {
    text-align: center;
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

img {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
}

button {
    margin-top: 20px;
    padding: 10px 15px;
    border: none;
    background-color: #007bff;
    color: white;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

```
### js file
```javascript
const images = [
    'static/images/sample-image.jpg',
    'static/images/sample-image2.jpg' // Add another image in the images folder
    
];

let currentIndex = 0;

document.getElementById('changeImageButton').addEventListener('click', () => {
    currentIndex = (currentIndex + 1) % images.length;
    document.getElementById('image').src = images[currentIndex];
});

```
### setttings.py
```python
STATICFILES_DIRS = [
    BASE_DIR / "static",
    
]
```
