That's normal on newer Ubuntu versions. Ubuntu protects the system Python using **PEP 668**, so `pip` won't install packages globally.

 The recommended solution is a **virtual environment (`venv`)**.

 ### 1\. Install venv support

```
sudo apt update
sudo apt install -y python3-venv
```

 If you're using Ubuntu with Python 3.12, you can also install:

```
sudo apt install -y python3-full
```

 ### 2\. Create a project directory

```
mkdir flask-api
cd flask-api
```

 ### 3\. Create a virtual environment

```
python3 -m venv venv
```

 This creates:

```
flask-api/
├── venv/
```

 ### 4\. Activate it

```
source venv/bin/activate
```

 Your terminal should now look something like:

```
(venv) ubuntu@server:~/flask-api$
```

 ### 5\. Install Flask

 Now this will work:

```
pip install flask
```

 Check:

```
pip show flask
```

 ### 6\. Create your API

```
nano app.py
```

 Put this inside:

```
from flask import Flask, jsonify

app = Flask(__name__)

@app.route("/hello")
def hello():
    return jsonify({
        "message": "Hello World"
    })

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

 Run:

```
python app.py
```

 You should see:

```
Running on http://127.0.0.1:5000
```

 Test from another terminal:

```
curl http://localhost:5000/hello
```

 Response:

```
{
  "message": "Hello World"
}
```

 ### 7\. When you're finished

 Leave the virtual environment with:

```
deactivate
```

 Later, when you come back to the project:

```
cd ~/flask-api
source venv/bin/activate
python app.py
```

 ### Don't use this unless you really need it

 You _can_ bypass Ubuntu's protection:

```
pip install flask --break-system-packages
```

 But I recommend **not** doing this for your Flask project. Use `venv` instead.

 The important concept is:

```
Ubuntu system Python
       ↓
    DON'T pip install globally
       ↓
    python3 -m venv venv
       ↓
    source venv/bin/activate
       ↓
    pip install flask
```

 This approach also works for `requests`, `FastAPI`, `Django`, and most other Python packages.
