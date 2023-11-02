# Django ORM Web Application

## AIM
To develop a Django application to store and retrieve data from a database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

![Screenshot from 2023-10-31 11-39-35](https://github.com/SaravananPV3010/django-orm-app/assets/139754526/61384ad7-7a0f-4799-aaf9-32b7ec3f8913)



## DESIGN STEPS

### STEP 1
         First folder ex02 is created and move into the directory.
        - mkdir ex02
        - cd ex02
### STEP 2
         Fork the repository https://github.com/gowriganeshns/django-orm-app.git .
### STEP 3
         Clone the repository inside the folder ex02.
         - git clone https://github.com/SaravananPV3010/django-orm-app.git
### STEP 4
         After cloning the folder with the repository,now move into the django-orm-appfolder.
         - cd django-orm-app
### STEP 5
         Create the django project folder.
         - django-admin startproj myproj
         Move into the folder myproj where manage.py file is located.
         Create new app and name it myapp
         - python3 manage.py startapp myapp
### STEP 6
         Visit settings.py and add ‘myapp’ in the configuration INSTALLED_APPS.
         - 'myapp'
### STEP 7
         Create Admin account.
         - python manage.py makemigrations
         - python manage.py migrate
### STEP 8
         Create a Superuser.
         - python manage.py createsuperuser
         Add the username and email for the superuser as follows (example).
         - Username (leave blank to use 'django'): admin
         - Email address: admin@example.com
         The next prompt in the shell is for your password. Add a strong password and press the Enter key to confirm it once again.
         - Password:
         - Password (again):
         You should see the following message on your screen : Superuser created successfully.
### STEP 9
         Visit the admin app athttp://127.0.0.1:8000/admin/. Log in with the superuser account that you have created.
         - python manage.py runserver 0:8000
### STEP 10
         create models.py as follows.

         from django.db import models
         from django.contrib import admin
         # Create your models here.

         class Student(models.Model):
         referencenumber = models.CharField(max_length=10, help_text="Your Reference Nummber")
         name = models.CharField(max_length=100)
         age = models.IntegerField()
         email = models.EmailField()
         mobile_number = models.IntegerField()
    
         class StudentAdmin(admin.ModelAdmin):
         list_display = ('referencenumber','name','age','email','mobile_number')

         class Employee (models.Model):
         emp_id=models.CharField(primary_key=True,max_length=4,help_text=' Employee ID')
         ename=models.CharField(max_length=50)
         post=models.CharField(max_length=20)
         salary=models.IntegerField()

         class EmployeeAdmin(admin.ModelAdmin):
         list_display=('emp_id','ename','post','salary')from django.contrib import admin
### STEP 11
         create admins.py as follows.

         from django.contrib import admin
         from .models import Student,StudentAdmin,Employee,EmployeeAdmin

         # Register your models here.
         admin.site.register(Student,StudentAdmin)
         admin.site.register(Employee,EmployeeAdmin)
### STEP 12
         Create DataBase as follows.
         1) Make Migrations
         - python manage.py makemigrations myapp
         Migrations for 'myapp':
         myapp/migrations/0001_initial.py
         Create model Student
         2) Then Migrate
         - python manage.py migrate myapp
         Apply all migrations: myapp
         Running migrations:
         Applying myapp.0001_initial... OK
### STEP 13
         Django Administration is Created.
         - python manage.py runserver 0:8000
### STEP 14
         Now add 10 Employees in Django Administration Page.
         Take a screenshot of that page and upload it in the moodle.
          
## PROGRAM

model.py code :
```
from django.db import models
from django.contrib import admin
# Create your models here.

class Student(models.Model):
    referencenumber = models.CharField(max_length=10, help_text="Your Reference Nummber")
    name = models.CharField(max_length=100)
    age = models.IntegerField()
    email = models.EmailField()
    mobile_number = models.IntegerField()
    
class StudentAdmin(admin.ModelAdmin):
    list_display = ('referencenumber','name','age','email','mobile_number')

class Employee (models.Model):
    emp_id=models.CharField(primary_key=True,max_length=4,help_text=' Employee ID')
    ename=models.CharField(max_length=50)
    post=models.CharField(max_length=20)
    salary=models.IntegerField()

class EmployeeAdmin(admin.ModelAdmin):
    list_display=('emp_id','ename','post','salary')
```
admin.py code:
```
from django.contrib import admin
from .models import Student,StudentAdmin,Employee,EmployeeAdmin

# Register your models here.
admin.site.register(Student,StudentAdmin)
admin.site.register(Employee,EmployeeAdmin)
```

## OUTPUT


![Screenshot from 2023-10-31 10-46-50](https://github.com/SaravananPV3010/django-orm-app/assets/139754526/5cd5fde0-2250-43f5-9ead-f7d3bf612b54)



## RESULT
Django application to store and retrieve data from a database using Object Relational Mapping(ORM) is developed.
