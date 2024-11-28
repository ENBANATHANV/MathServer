# Ex.05 Design a Website for Server Side Processing
## Date:28/11/2024

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
hello.html

<html>
<head>
<style>

</style>
</head>
<body>
    <div class="edge">
        <div class="box">
            <h1>POWER OF A LAMP FILAMENT</h1>
            <form method="POST">
                {% csrf_token %}
            </div>
            <h2>Enbanathan V (24001750)</h2>
                <div class="formelt">
                    <br>
                    Intensity : <input type="text" name="Intensity" value="{{I}}"></input>(in W/m <sup> 2 </sup>) <br>
                </div>
                <div class="formelt">
                    <br>
                    Resistance : <input type="text" name="Resistance" value="{{R}}"></input>(in ohm)<br>

                </div>
                
                <div  class="formelt">
                    <br>
                    <input type="submit" value="calculate"></input><br>
                </div>
                <div class="formelt">
                    <br>
                power : <input type="text" name="power" value="{{power}}"></input>(in watt)<br>
                </div>
 
            </form>
    </div>
</body>
</html>

loki.css

.edge
 { display: block;
    margin-top: 400px;
    margin-bottom: auto;
    margin-left: auto;
    margin-right: auto;
    border-style: dashed;
    border-color: red;
   background-color: yellow;
    padding-top: 50px;
    padding-right: 50px;
    padding-bottom: 50px;
    padding-left: 80px;
    width: 25%;
    flex-direction: column;
    
  }
  body{
    background-color: blueviolet;
  }
div.formelt
{
    font-size: 150%;
   color: red;
  
    
}
div.box
{
  color: blue;
  text-align: center;
  font-style: unset;
  
}
input
{
  padding: 10px;
  border: 1px solid;
  border-radius: 3px;
  width: 50%;
  align-items: center;
}

views.py

from django.shortcuts import render 
def powerbulb(request): 
    context={} 
    context['power'] = "0" 
    context['I'] = "0" 
    context['R'] = "0" 
    if request.method == 'POST': 
        print("POST method is used")
        I = request.POST.get('Intensity','0')
        R = request.POST.get('Resistance','0')
        print('request=',request) 
        print('Intensity=',I) 
        print('Resistance=',R) 
        power = (int(I) * int(I)) * int(R) 
        context['power'] = power
        context['I'] = I
        context['R'] = R
        print('power=',power) 
    return render(request,'leo/hello.html',context)


    urls.py

    from django.contrib import admin 
from django.urls import path 
from leo import views 
urlpatterns = [ 
    path('admin/', admin.site.urls), 
    path('powerofalamp/',views.powerbulb,name="powerofalamp"),
    path('',views.powerbulb,name="powerofalamp")
]

```

## SERVER SIDE PROCESSING:
![alt text](<Screenshot (101).png>)

## HOMEPAGE:
![alt text](<Screenshot (100).png>)

## RESULT:
The program for performing server side processing is completed successfully.
