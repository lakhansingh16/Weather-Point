Harvard's CS50 Web Programming with Python and Javascript 2020 <br>

---

## **_Capstone project by Lakhan Singh Barod_**

Project Name: Weather Point<br>
Project Completed on: 5/02/22<br>

[Lakhan Singh Barod's Github](https://github.com/lakhansingh16) <br>
[Video Demonstration of App](https://youtu.be/cL5Y6B8zTiM) <br>
Email: lakhanbarod165@gmail.com

### **About:**

This project is my submission for the final project of CS50's Web development course with Python
and Javascript. This project uses Python's Django framework, HTML, CSS and Javascript to display
weather of a particular location using data provided by OpenWeatherMap API. It displays user location, time-zone, weather specifics for current day as well as of the following week.

### **Project distinctiveness and complexities:**

This project is fairly distinct from the projects provided in the previous lectures of this course
as it implements a totally different service that was not previously implemented in any project.
It uses a third party API to get weather data and dynamically generate the contents of the webpage
using Javascript. It also uses Django models to store user information and only display the service
if the user registers first and logs in to the web application.

The project's frontend is built using **Javascript** and Django's html templates as well. **Bootstrap** CSS library was also integrated to assist with styling and make the website more aesthetic.

The project uses Django's predefined abstractuser model and other Django services like user authentication, login and logout and also security features like csrf tokens.

### **Files:**

The following is the file structure of the project where I added or modified. Default project files are ommitted.

```
/ (folder)
-- (files)

/Weather - main project folder
 --README.md - this file
  /geo - Django main project folder
   --asgi.py - asynconous web servers and wrapped in middleware
   --settings.py - slightly modified settings
   --urls.py - path configuration
   --utils.py - used for jwt response handler
  /weather - Django weather app
   --templates\weather - templates used to test initial build
   --static\weather - static files including styles.css and weather.js which performs major tasks.
   --admin.py - admin settings for model view
   --app.py - app configuration
   --models.py - database models
   --urls.py - all standard HTTP request routing handled here
   --views.py - This file implements the functions that render views of the app.

```
---

<br>

### **How the project works:**

This project works in a fairly simple and user friendly manner. Any new user has to first register on the web application to access the service. If the user is registered and not logged in, they can log in to access the service. The app uses Django authentication services to perform this task and stores cache to remember the user if they log in frequently. Once the user logs in, the service requires access to the users' location to generate weather data for their particular location. Then their location information is used to get weather data from a third party service and they are displayed won their screen with their timezone, their coordinates, the time in their timezone, and their weather conditions like day and night temperatures, humidity, pressure, sunrise and sunset times.  Also, we provide with the weather data for the following week on the same page along with icons that match the weather desciption. At no point is the user's location information stored anywhere or provided to anyone except the API service to fetch weather data.

<br>

### **How to run application:**

1. Navigate to the project folder


2. Initialize the database with makemigrations, migrate, then create superuser.

```
py manage.py makemigrations
py manage.py migrate
py manage.py createsuperuser
```

3. Launch the Django server. If set up correctly, server will launch on http://127.0.0.1:8000/.

```
py manange.py runserver
```