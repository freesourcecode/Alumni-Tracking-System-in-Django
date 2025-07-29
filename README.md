# Alumni Tracking System in Django with Source Code

The **Alumni Tracking System Project in Djang**o created based on python, Django, and MYSQL Database.

The A**lumni Tracking System’s** flow, university/college alumni will register on the website, and this process will include school management verification in order to enlist the alumnus/alumna as a website user.

An **Alumni Tracking System**, the admin has verified the user as an alumnus of the school, the alumni user may begin to explore the system’s functionality or functionalities on their own, such as work openings posted by other alumni or admin, a calendar of upcoming events, and joining the alumni connect chat.
>[!NOTE]
> To start creating an **Alumni Tracking System Project in Python Django**, makes sure that you have PyCharm Professional IDE Installed in your computer.

## Alumni Tracking System in Django: Student Features

* **Login Page**

Student enter their website credentials on this page to gain access to all of the website’s features.

* **Register Page**

The page where new Student created their login credentials for the website.

* **Home Page**

When Student visit the website, this is the system’s default page. 
This page shows the home, current event, colleges, alumni, alumni connect chat and profile.

* **Manage Profile Page** 

This is the page where the student can update their profile.

* **View Current Event**

This is the page where the student can view current event posted by admin.

* **View Colleges**

This is the page where the student can view school college.

## How to Create a Project Alumni Tracking System in Django?

Here are the steps on how to create an **Alumni Tracking System in Django with Source Code**.

1. **Open file**.

First, open “pycharm professional” after that click “file” and click “new project”.

<img width="484" height="453" alt="image" src="https://github.com/user-attachments/assets/d49a0d65-c954-4579-bb5c-29972561bdb8" />


2. **Choose Django.**

Next, after click “new project“, choose “Django” and click.

<img width="152" height="325" alt="image" src="https://github.com/user-attachments/assets/1fc332b7-f507-49e5-8585-9a19e939447f" />

3. S**elect file location**.

Then, select a file location wherever you want.

4. Create application name.
After that, name your application.

5. **Click create**.
Lastly, finish creating project by clicking “create” button.

6. **Start Coding**.

Finally, we will now start adding functionality to our Django Framework by adding some functional codes.

## Functionality and Codes of the Alumni Tracking System in Django

* Create template for the homepage in Alumni Tracking System Project in Django.

In this section, we will learn on how create a templates for the homepage. 

To start with, add the following code in your base.html under the folder of /templates/.


```
{% load static %}
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>Alumni Tracker</title>
    <meta content="width=device-width, initial-scale=1.0" name="viewport">
    <meta content="" name="keywords">
    <meta content="" name="description">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link href="{% static 'base/img/title.jpg'%} " rel="icon">
    <link href="{% static 'base/img/title.jpg' %}" rel="apple-touch-icon">
    <link href="https://fonts.googleapis.com/css?family=Open+Sans:300,300i,400,400i,700,700i|Montserrat:300,400,500,700" rel="stylesheet">
    <link href="//maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
    <link href="{%static 'base/lib/bootstrap/css/bootstrap.min.css'%}" rel="stylesheet">
    <link href="{% static 'base/lib/font-awesome/css/font-awesome.min.css' %}" rel="stylesheet">
    <link href="{% static 'base/lib/animate/animate.min.css'%}" rel="stylesheet">
    <link href="{% static 'base/lib/ionicons/css/ionicons.min.css' %}" rel="stylesheet">
    <link href="{% static 'base/lib/owlcarousel/assets/owl.carousel.min.css'%}" rel="stylesheet">
    <link href="{% static 'base/css/style.css'%}" rel="stylesheet">
    <link href="{% static 'base/header/css/style.css' %}" rel="stylesheet" type="text/css" />
    <link href="https://fonts.googleapis.com/css?family=Poppins:300,400,500,600,700" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Lora:400,400i,700,700i&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Abril+Fatface&display=swap" rel="stylesheet">
</head>

<body>
    <header class="header-section" style="margin-bottom: 76px">
        <nav class="navbar navbar-expand-md navbar-dark bg-primary site-navbar fixed-top">
            <a class="navbar-brand site-logo" href="{% url 'home' %}">
                <h2><span class="text-light">Alumni</span> Tracker System</h2>
            </a>
            <button class="navbar-toggler d-lg-none" type="button" data-toggle="collapse" data-target="#collapsibleNavId" aria-controls="collapsibleNavId" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="collapsibleNavId">
                <ul class="navbar-nav ml-auto mt-2 mt-lg-0">
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'home' %}">Home <span class="sr-only">(current)</span></a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Current Events</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'show-college' %}">Colleges</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'show-alumni' %}">Alumni</a>
                    </li>
                    {% if request.user.is_authenticated %}
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'logout' %}">Logout</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Alumni Connect Chat</a>
                    </li>
                    {%if not request.user.is_college %}
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'alumni-profile' request.user.id%}">Profile</a>
                    </li>
                    {%elif request.user.is_college %}
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'pending-query' %}">Pending Queries</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'college-profile' request.user.id %}">Profile</a>
                    </li>
                    {%endif%}
                    {% else %}
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'login' %}">Login</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'alumni_signup' %}">Alumni-Signup</a>
                    </li>
                    {% endif %}
                    {% if request.user.is_authenticated and request.user.is_superuser %}
                    <li class="nav-item">
                        <a class="nav-link" href="{% url 'college_signup' %}">College-Signup</a>
                    </li>
                    {% endif %}
                </ul>
            </div>
        </nav>
    </header>
    {% block content %}
    {% endblock %}
    <footer id="footer">
        <div class="container">
            <div class="copyright">
                &copy; Copyright <strong>Alumin Tracking System 2021</strong>. All Rights Reserved
            </div>
        </div>
    </footer>
    <script src="{%static 'base/header/js/jquery-3.2.1.min.js' %}"></script>
    <script src="{%static 'base/header/js/bootstrap.min.js' %}"></script>
    <script src="{%static 'base/header/js/owl.carousel.min.js' %}"></script>
    <script src="{%static 'base/header/js/main.js' %}"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"></script>
</body>

</html>
```


### 📌 Here's the full documentation for the [Alumni Tracking System in Django](https://itsourcecode.com/free-projects/python-projects/alumni-tracking-system-in-django-with-source-code/)
