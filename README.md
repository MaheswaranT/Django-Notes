# Django-Notes

### History of Django:
- Django was created in 2003 by two developers, Adrian Holovaty and Simon Willison, while working at a newspaper.  
- It was designed to make building websites faster and easier, especially for news sites.  
- In 2005, Django became open-source, meaning anyone could use it for free.  
- The name "Django" comes from Django Reinhardt, a famous jazz guitarist.

---

### Advantages of Django:
1. **Fast Development:**  
   Django helps build websites quickly with tools like a login system, admin panel, and database connections already included.  

2. **Safe and Secure:**  
   It protects your website from common security problems like hacking and data leaks.  

3. **Works for Big and Small Websites:**  
   Django is strong enough to handle big sites like YouTube and Instagram but also works for smaller ones.  

4. **Uses Python:**  
   Python is simple to learn, so working with Django is easier if you know Python.

5. **Easy Maintenance:**  
   Django’s structure keeps the code clean and organized, making it easier to update or fix later.  

6. **Large Community:**  
   Lots of people use Django, so there are many tutorials, tools, and help available online.  

---

### Disadvantages of Django:
1. **Too Big for Small Projects:**  
   If your website is simple, Django might feel like using a big tool for a small job.  

2. **Takes Time to Learn:**  
   Beginners might find Django confusing because it has so many features.

3. **Not Fully Real-time:**  
   Django isn’t the best choice for apps that need live updates, like chat apps.

4. **Heavy Framework:**  
   Django comes with everything included, which can feel slow or unnecessary for some projects.  

---

This version keeps it easy to understand for beginners!

Before learning Django, we need to understand the basics of Python, including its syntax and how it works. This is important because Django is a web framework developed using Python.  
We must understand functions, arguments/parameters, modules, and packages in Python to learn Django effectively.

**Modules:** A module is a single file that contains a group of functions, classes, or variables.  
Ways of using modules:  
- `import module`  
- `from module import *`  
- `import module as aliasname`  
- `from module import function as aliasname`  

**Packages:** A package is a collection of modules or related modules. A package is similar to a folder, but it includes an `__init__.py` file, which is known as a script file. To convert any folder into a Python package, we must add an `__init__.py` file. If a folder does not include an `__init__.py` file, it is considered a normal folder.

Django is an open-source macro web framework.  
Django offers high scalability, allowing it to perform well whether there are 100, 1,000, or even 10,000 users.

**Design Pattern:** The most common and familiar design pattern is MVC (Model View Controller).  
A design pattern separates an application into three parts:  
- **Model:** Manages the application's data and business logic.  
- **View:** Handles the layout and display of the data.  
- **Controller:** Routes commands to the model and view parts.  

**Example: Restaurant**  
The customer is the view, the waiter is the controller, the chef is the model, and the fridge is the data.

**Note:** Django uses the MVT (Model View Template) method instead of MVC.  
Applications developed using Django (MVT method): YouTube, Dropbox.

---

### Install Django:
```
pip install django
```

### Create a project:
```
django-admin startproject myproject
```

After creating a Django project, the default structure looks like this:  
```
project/
    - manage.py
    - myproject/
        -- __init__.py
        -- settings.py
        -- urls.py
        -- asgi.py
        -- wsgi.py
```

**File Descriptions:**  
- **`__init__.py`:**  
  A blank Python script file.  
  Used to view a folder as a Python package.  
  Django will consider the particular folder as a Python package.  

- **`settings.py`:**  
  Used to define project settings and configuration, including installed applications, database configuration, and middleware configuration.  

- **`urls.py`:**  
  A collection of links that we create for our projects.  
  All URL patterns are stored here.  

- **`wsgi.py`:**  
  Web Server Gateway Interface.  
  This file is used when deploying the application to a production server.  
  - DEV Environment  
  - UAT (User Acceptance Test) Environment  
  - PROD Environment  

- **`asgi.py`:**  
  Used for asynchronous file transformation.  
  - **Synchronous:** Represents a website where the whole frame refreshes.  
  - **Asynchronous:** Represents a website where only a specific frame refreshes.  

- **`manage.py`:**  
  Usages:  
  - Running the server  
  - Running apps  
  - Creating migrations  

---

### Runserver:
```
py manage.py runserver
```
Open the browser and visit:  
[http://127.0.0.1:8000/](http://127.0.0.1:8000/)  

The website will show:  
"The install worked successfully! Congratulations."

**Role of Webserver:**  
Providing an environment to run web applications.  
- **Server:** Accepts the HTTP request and provides an HTTP response.

---

### Web Application Creation:
```
py manage.py startapp myapp
```

**Structure of `myapp/`:**  
```
myapp/
- __init__.py
- admin.py
- apps.py
- models.py
- tests.py
- views.py
```

**File Descriptions:**  
- **`admin.py`:**  
  The admin interface.  
  This file is used to register models with the Django admin site, allowing you to manage your models and their data through the Django admin interface.  
  You import your models and then use `admin.site.register(model_name)` to make them accessible in the admin interface.  
  It is a convenient way to handle CRUD operations without writing custom views.  

- **`models.py`:**  
  Here, we define database models.  
  Each model class represents a table in the database.  
  Attributes of the model class represent fields in that table.  
  We can define fields like `CharField`, `IntegerField`, `ForeignKey`, etc.  
  `models.py` serves as the blueprint for our database schema.  

- **`tests.py`:**  
  This is where we write test cases for Django applications.  
  These tests help ensure that the code behaves as expected and that any changes do not inadvertently break existing functionality.  
  We can write unit tests, integration tests, and even end-to-end tests to cover different aspects.  
  Testing is crucial for maintaining the reliability and stability of Django projects.  

- **`views.py`:**  
  Contains function-based or class-based views.  
  `views.py` defines the logic for handling incoming HTTP requests and returning appropriate HTTP responses.  
  Views are Python functions or classes that receive a request object and return a response object.  
  They can:  
  - Fetch data from databases  
  - Process form submissions  
  - Render templates  
  - Handle other tasks  
  `views.py` plays a crucial role in Django's MVT architecture, managing the presentation layer of web applications.  

- **Migration folder:**  
  This folder contains files that track changes to the database schema over time.  
  When changes are made to models in `models.py` (e.g., adding fields or altering existing ones), you run the `makemigrations` command to generate migration files.  
  Migration files are Python scripts that describe the changes to apply to the database schema.  
  Running the `migrate` command applies these migrations, ensuring the database schema stays in sync with the models.

---

### Flow of Django Project Setup:
1. **Create a Django project:**  
   ```
   django-admin startproject projectname
   ```

2. **Create a Django application:**  
   ```
   py manage.py startapp appname
   ```

3. **Add the application to the project:**  
   Update `settings.py` -> `INSTALLED_APPS`.

4. **Define business logic:**  
   Write views in `views.py`.

5. **Set up URLs:**  
   Configure `urls.py`.

6. **Run the server:**  
   ```
   py manage.py runserver
   ```
