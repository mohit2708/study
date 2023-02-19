# Python interview questions

#### Table of Contents

### **Ques. What is Django?**
* Django—pronounced “Jango,”. Django is a free and open source web application framework written in Python.
* Django follows the MVT (Model View Template) pattern which is based on the Model View Controller architecture.

### **What is the latest version of Django?**
The latest version of Django is Django 4.1.

### **Ques. Explain Django architecture?**
* Django follows a software design pattern called a MVT(Model view Template) architecture.
**Model:-** It helps in handling the databse. they provide the option to create edit and query data records in the databse.
**Template:-** The template is a presentation layer. It define the structure of file layout to present data in web page. it is an html file mixed with django template language.
**View:-** the view is used to execute the business logic and intrect with a model to carry data and renders a template.
* url request -> manage.py -> setting.py ->urls.py -> views.py -> models.py -> template.

### **Ques. Explain the django project directory structure?**
<ul>
    <li><b>manage.py</b> - A command-line utility that allows you to interact with your Django project</li>
    <li><b>__init__.py</b> - An empty file that tells Python that the current directory should be considered as a Python package</li>
    <li><b>settings.py</b> - Comprises the configurations of the current project like DB connections.</li>
    <li><b>urls.py</b> - All the URLs of the project are present here</li>
    <li><b>wsgi.py</b> - This is an entry point for your application which is used by the web servers to serve the project you have created.</li>
</ul>

### **Give a brief about the settings.py file?**
As the name implies, 
* it's the main settings file of the Django file. Everything inside the Django project, 
* like databases, 
* middlewares, 
* backend engines, 
* templating engines, 
* installed applications, 
* static file addresses, 
* main URL configurations, 
* allowed hosts and servers, 
* and security key stores in this file as a dictionary or list.

So when Django files start, it first executes the settings.py file and then loads the respective databases and engines to quickly serve the request.


### **What are static files in Django? And how can you set them?**
static files are the files that serve the purpose of additional purposes such as images, CSS, or JavaScript files. Static files managed by “**django.contrib.staticfiles**”. There are three main things to do to set up static files in Django:
1. Set STATIC_ROOT in settings.py
2. Run manage.py collect static
3. Set up a Static Files entry on the PythonAnywhere web tab


### **What is the difference between Python and Django?**
* Both Python and Django are intertwined but not the same. Python is a programming language used for various application developments: machine learning, artificial intelligence, desktop apps, etc.
* Django is a Python web framework used for full-stack app development and server development.
* Using core Python, you can build an app from scratch or craft the app with Django using prewritten bits of code.

### **What is Jinja templating?**
Jinja Templating is a very popular templating engine for Python, the latest version is Jinja2. 
* Sandbox Execution - This is a sandbox (or a protected) framework for automating the testing process
* HTML Escaping - It provides automatic HTML Escaping as <, >, & characters have special values in templates and if using a regular text, these symbols can lead to XSS Attacks which Jinja deals with automatically.
* Template Inheritance
* Generates HTML templates much faster than default engine
* Easier to debug as compared to the default engine.

### **Ques. create a migration file inside the migration folder?**
```python
python manage.py makemigrations

# after creation a migration to reflect in the database.
python manage.py migrate

# single migration 
python manage.py sqlmigrate app_name migrate_name

# to see all migrations.
python manage.py showmigrations

# to see specific migrations by specifying app name
python manage.py showmigrations app_name
```


### **Ques. What are models in Django?**
A model is a class that represents table or collection in our DB, and where every attribute of the class is a field of the table or collection. Models are defined in the app/models.py (in our example: myapp/models.py)
```python
from django.db import models

class Employee(models.Model):

    id = models.AutoField('Id', primary_key=True)
    first_name = models.CharField('First name', max_length=15, null = True)
    last_name = models.CharField('Last name', max_length=16, blank=True)
    email = models.EmailField(max_length = 255, unique=True, null = True)
    user_name   = models.CharField(max_length=50, unique=True, null = True, error_messages ={
                    "unique":"The User Name Field you entered is unique."
                    })
    number = models.IntegerField()
    dof = models.DateField('Birthday')

    class Meta:
      db_table = "employee"
  
   	def __str__(self):
		  return "{} {}".formet(self.first_name, self.last_name)
```

### **Ques. Name some companies that make use of Django?**
Some of the companies that make use of Django are Instagram, DISCUS, Mozilla Firefox, YouTube, Pinterest, Reddit, etc.

#### Ques. What are the features of Django?
* SEO Optimized
* Extremely fast

### **Ques. How to create virtual Enviroment and How can Activate?**
```python
python -m venv virtual-name

# Activate Process
virtual Enviroment Folder -> Scripts -> Activate
```

### **Ques. How to install Django and Uninstall Django?**
```python
# Install Django
pip install django
python -m pip install django

# Uninstall Django
pip uninstall django
```

### **Ques. How do you check for the version of Django installed on your system?**
```python
# you can open the command prompt and enter the following command:
python -m django –-version

# You can also try to import Django and use the get_version() method as follows:
import django
print(django.get_version())
```

### **Ques. Check all the version of install modules?**
```python
pip freeze
```
### **Ques. What is the difference between a project and an app in Django?**
* in simple words Project is the entire Django application and an app is a module inside the project that deals with one specific use case. For eg, payment system(app) in the eCommerce app(Project)
* A project, is a collection of these apps.

### **Ques. How to create Project and App?**
```python
# Create the Project
django-admin startproject projectName

# Create the app
python manage.py startapp app_name
```

### **Project Directery**
```python
project
  manage.py
  project
    __init__.py
    asgi
    settings  # congigration of the project like db connection, middleware.
    urls      # urls
    wsgi      # this is entery point server related details
```

### **App Directery**
```python
app
  __init__.py
  admin.py
  apps.py
  migrations
    __init__.py
  models.py
  tests,py
  views.py
```





### **Ques. How to Run Server?**
```python
# run a project
python manage.py runserver

#change a port number
python manage.py runserver:8484

# change the server ip and port
python manage.py runserver0.0.0.0:8484
```

### **Ques. create a superuser**
```python
# create a super user
python manage.py createsuperuser

username: ------
email address: ------
password: -------
password(again): ------
superuser created successfully
```

### **Ques. What is the django command to view a databse schema of an existing(or legacy) databse?**
```python
python manage.py inspectdb
```

### **Ques. How to view all items in the Model using django QuerySet?**
```python
Users.objects.all()

# where "Users" is a model name
```

### **Ques. How to filter items in the model using django QuerySet?**
```python
Users.objects.filter(name="mohit")

# where "Users" is a model name
```

### **Ques. How to get a particular items in the model using django QuerySet?**
```python
Users.objects.get(id=25)

# where "Users" is a model name
```




### **Ques. Model Meta Options?**
1. abstract
   If abstract = True, this model will be an abstract  base class
```python
class student(models.Model):
  class Meta:
      abstract = True
```

2. app_label
   If a model is defined outside of applications in INSTALLED_APPS, it must declare which app  it belongs to:
```python
class student(models.Model):
  class Meta:
      app_label = 'myapp' # add app name here
```

3. verbose_name:- verbose_name is basically a human-readable name for your model
```python
class student(models.Model):
  class Meta:
      verbose_name = "stu" # add verbose_name  here
```

4. ordering:- Ordering is basically used to change the order of your model fields.
```python
class student(models.Model):
  class Meta:
      ordering = [-1]
```

5. proxy:- If we add proxy = True a model which subclasses another model will be treated as a proxy model
```python
class Student(Teacher):
  class Meta:
      proxy = True
```

6. permissions:- Extra permissions to enter into the permissions table when creating this object. Add, change, delete and view permissions are automatically created for each model.
```python
class student(models.Model):
  class Meta:
      permissions = []
```

7. db_table:- We can overwrite the table name by using db_table in meta class.
```python
class student(models.Model):
  class Meta:
      db_table = 'table_name'
```

8. get_latest_by:- It returns the latest object in the table based on the given field, used for typically DateField, DateTimeField, or IntegerField.
```python
class student(models.Model):
  class Meta:
      get_latest_by = "order_date"
```

### **Ques. Meta Class in Models?**
Model Meta is basically the inner class of your model class. Model Meta is basically used to change the behavior of your model fields like changing order options,verbose_name, and a lot of other options. It’s completely optional to add a Meta class to your model.
```python
class student(models.Model):
    class Meta:
        options........
```


### **Ques. What is CRUD operations Django?**
Django is a Python-based web framework that follows the MVT (Model View Template) pattern and allows you to quickly create web applications. It offers built-in class-based generic views for CRUD operations. CRUD in general means Creating, Retrieving, Updating and Deleting operations on a table in a database.

What is class based view in Django?
Class-based view is an alternative to function-based view. They do not replace function-based views, but have some distinct differences and advantages over function-based views.

What is generic views in Django?
Django generic views have been developed as shortcuts for common usage methods such as displaying object details.
They take some of the common methods found in view development and abstract them so that you can quickly write common views of data without writing too much code.

What is DetailView in Django?
Django DetailView should be used when you want to present detail of a single model instance. Its purpose is to use with only one object.



