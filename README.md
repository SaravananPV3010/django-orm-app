# Django ORM Web Application

## AIM
To develop a Django application to store and retrieve data from a database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

![Screenshot from 2023-10-31 11-39-35](https://github.com/SaravananPV3010/django-orm-app/assets/139754526/61384ad7-7a0f-4799-aaf9-32b7ec3f8913)
## DESIGN STEPS
### STEP 1:
   Clone the repository from github .

### STEP 2:
   Create an admin page for Django .

### STEP 3:
   Create an app and edit settings.py .

### STEP 4:
   Makemigration and migrate the changes .

### STEP 5:
   Create admin user and write python code for admin and models .

### STEP 6:
   Make all the migration to my app .

### STEP 7:
   Create a students database with 10 fields using runservercommand .

          
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
