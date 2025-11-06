## ⚙️ **1.3 Installing Python and Setting Up the Environment**

---

### **1.3.1 Step 1 — Check if Python is Already Installed**

Before installing, check whether Python is already available on your system.

#### 🪟 **For Windows**

1. Open **Command Prompt (cmd)**.
2. Type:

   ```bash
   python --version
   ```

   or

   ```bash
   py --version
   ```

   ✅ If Python is installed, you’ll see something like:

   ```
   Python 3.12.2
   ```

   ❌ If not, you’ll see an error such as *“Python is not recognized…”* — in that case, proceed to install.

#### 🍎 **For macOS / Linux**

Open **Terminal** and type:

```bash
python3 --version
```

If you get a version number, Python is installed; if not, install it using your package manager.

---

### **1.3.2 Step 2 — Download and Install Python**

#### 🪟 **Windows Installation**

1. Visit the official Python website:
   🔗 [https://www.python.org/downloads/](https://www.python.org/downloads/)
2. Click **Download Python 3.x.x** (latest stable release).
3. **Important:** On the first screen, **check the box** that says:

   ```
   ✅ Add Python 3.x to PATH
   ```
4. Then click **Install Now** and wait for the setup to finish.
5. Verify installation by opening CMD and typing:

   ```bash
   python
   ```

   You should see the Python interactive shell:

   ```
   >>> 
   ```

#### 🍎 **macOS Installation**

* Python 2 may come pre-installed, but you’ll need Python 3.
* Easiest way:

  ```bash
  brew install python
  ```

  (Requires [Homebrew](https://brew.sh) installed)

#### 🐧 **Linux Installation**

Python 3 often comes pre-installed.
If not, install it using:

```bash
sudo apt update
sudo apt install python3
```

---

### **1.3.3 Step 3 — Verify the Installation**

Open your terminal or command prompt and run:

```bash
python --version
```

or

```bash
python3 --version
```

✅ Output example:

```
Python 3.12.2
```

If you see that, congratulations — Python is installed successfully!

---

### **1.3.4 Step 4 — Installing an IDE or Code Editor**

You can write Python in any text editor, but using a **code editor or IDE** makes development much easier.

| **Editor / IDE**             | **Best For**                   | **Highlights**                            |
| ---------------------------- | ------------------------------ | ----------------------------------------- |
| **VS Code**                  | Beginners & professionals      | Free, lightweight, has Python extensions  |
| **PyCharm**                  | Professional development       | Smart code completion, debugging tools    |
| **Jupyter Notebook**         | Data science, machine learning | Interactive notebook interface            |
| **Thonny**                   | Absolute beginners             | Simple, clean interface                   |
| **IDLE** (comes with Python) | Beginners                      | Already included with Python installation |

💡 **Recommendation:** Start with **VS Code** or **Thonny**.

---

### **1.3.5 Step 5 — Setting Up VS Code for Python**

If you choose **Visual Studio Code (VS Code)**:

1. Download from [https://code.visualstudio.com](https://code.visualstudio.com)
2. Open VS Code and install the **Python extension** (from Microsoft).
3. Open a new folder → create a new file named `hello.py`.
4. Type:

   ```python
   print("Hello, Python!")
   ```
5. Run the file by clicking **Run ▶️** or pressing:

   ```
   Ctrl + F5 (Windows) / Cmd + F5 (Mac)
   ```

✅ You should see:

```
Hello, Python!
```

---

### **1.3.6 Step 6 — Try the Python Interactive Shell**

You can test short snippets directly in the **interactive shell**.

In your terminal, type:

```bash
python
```

You’ll enter the **Python REPL** (Read-Eval-Print Loop), where you can execute commands directly.

Example:

```python
>>> print("Welcome to Python!")
Welcome to Python!
>>> 2 + 3
5
>>> exit()
```

---

### **1.3.7 Step 7 — Install pip (Python Package Manager)**

**pip** is the tool that allows you to install external Python packages.

Check if it’s installed:

```bash
pip --version
```

If it’s missing, install it with:

```bash
python -m ensurepip --upgrade
```

✅ You can now install packages easily, for example:

```bash
pip install requests
```

---

### **1.3.8 Step 8 — Optional: Create a Virtual Environment**

A **virtual environment** lets you manage dependencies separately for each project.

```bash
python -m venv myenv
```

Activate it:

* **Windows:** `myenv\Scripts\activate`
* **macOS/Linux:** `source myenv/bin/activate`

Deactivate with:

```bash
deactivate
```

---

### **✅ Summary**

| **Task**                     | **Command / Step**                                        |
| ---------------------------- | --------------------------------------------------------- |
| Check version                | `python --version`                                        |
| Download Python              | [python.org/downloads](https://www.python.org/downloads/) |
| Install VS Code              | [code.visualstudio.com](https://code.visualstudio.com)    |
| Run your first script        | `python hello.py`                                         |
| Install a package            | `pip install packagename`                                 |
| Create a virtual environment | `python -m venv myenv`                                    |

---


