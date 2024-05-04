**create a new repository on the command line**
echo "# hello_django" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/movvamanoj/hello_django.git
git push -u origin main

**push an existing repository from the command line**
git remote add origin https://github.com/movvamanoj/hello_django.git
git branch -M main
git push -u origin main


Certainly! Here's a sample README.md file with instructions for setting up the Django project and running the "Hello, World!" application:

```markdown
# Hello Django

This is a simple Django application that displays a "Hello, World!" message.

## Setup Instructions

Follow these steps to set up the project:

### 1. Install Django

Ensure you have Python installed. Then, install Django using pip:

```bash
pip install django
```

### 2. Clone the Repository

Clone this repository to your local machine:

```bash
git clone <repository-url>
cd hello_django
```

### 3. Create Django Project

Create a new Django project named "hello_django":

```bash
django-admin startproject hello_django .
```

### 4. Create a Django App

Inside your project directory, create a Django app named "hello":

```bash
python manage.py startapp hello
```

### 5. Write View Function

Open the file `hello/views.py` and define a view function that returns a simple "Hello World" message:

```python
# hello/views.py
from django.http import HttpResponse

def hello_world(request):
    return HttpResponse("Hello, World!")
```

### 6. Configure URL Routing

Open the file `hello_django/urls.py` and configure URL routing to map a URL to the view function you just created:

```python
# hello_django/urls.py
from django.urls import path
from hello.views import hello_world

urlpatterns = [
    path('', hello_world),
]
```

### 7. Run the Development Server

Run the Django development server to test your application:

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/` in your web browser, and you should see the "Hello, World!" message.

## Project Structure

Your project structure should look like this:

```
hello_django/
│
├── hello_django/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
└── hello/
    ├── migrations/
    │   └── __init__.py
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── models.py
    ├── tests.py
    └── views.py
```

Now, your Django application should be up and running, displaying the "Hello, World!" message.
```

Feel free to adjust the formatting or add more details as needed! Let me know if you have any questions or if there's anything else I can assist you with.