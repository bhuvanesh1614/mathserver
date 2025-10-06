# Ex.05 Design a Website for Server Side Processing
# Date:2-10-2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body{
            background-image: linear-gradient(90deg,rgb(41, 244, 241),pink,violet,black,grey);
        }
    </style>
    <style>
        label,TT{
            color:maroon;
        }
    </style>
    <style>
        h2{
            color:rgb(118, 239, 13);
        }
    </style>
</head>
<body>
    <center>

    <h2><u><big>Power Calculator</big></u></h2> 
<form method="post"> 
{% csrf_token %} 
<label><big>CURRENT (A):</big></label><br> 
<input type="number" name="current" required><br><br><br>
<label><BIG>RESISTANCE (ohm):</BIG></label><br> 
<input type="number" name="resistance" required><br><br><br>
<button type="submit"><i><big>Calculate Power</big></i></button><br><br><br>
</form> 
<TT><big>POWER (W): {{ power }}</big></TT> 
</center>
</body> 
</html> 
from django.contrib import admin
from django.urls import path
from cal import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path("",views.pow,name='pow')
]
from django.shortcuts import render

def pow(request):
    current=""
    resistance=""
    power=None
    if request.method == "POST":
        current=float(request.POST.get("current"))
        resistance=float(request.POST.get("resistance"))
        power=current*current*resistance
        print(f"current:{current} A,Resistance:{resistance} ohm,power:{power:.2f}")
    return render(request,"power.html",{'power':power})


```

# SERVER SIDE PROCESSING:
![alt text](<Screenshot 2025-10-03 155516.png>)
![alt text](<Screenshot 2025-10-03 155738.png>)
![alt text](<Screenshot 2025-10-04 124332.png>)
![alt text](<Screenshot 2025-10-04 124400.png>)

# HOMEPAGE:
![alt text](<Screenshot 2025-10-03 155403.png>)

# RESULT:
The program for performing server side processing is completed successfully.
