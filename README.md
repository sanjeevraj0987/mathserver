# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Create a Django project.



### Step 2:
Create an App named (some app name)



### Step 3:
In the app folder ...create a folder named template.In template folder create an anoter folder named (app folder name).



### Step 4:
Create a html document in the template under app folder.



### Step 5:
In the html document design the page as required for getting the input values for doing mathematical calculation.



### Step 6:
Add the formula in views.py.

## PROGRAM :
HTML CODE:
```
<!DOCTYPE html>
<html>
<head>
   <meta charset='utf-8'>
   <meta http-equiv='X-UA-Compatible' content='IE=edge'>
   <title>Area of Rectangle</title>
   <meta name='viewport' content='width=device-width, initial-scale=1'>
   <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
   <script src='main.js'></script>
</head>
<style>
   *{
       box-sizing: border-box;
       font-family:Arial, Helvetica, sans-serif ;
   }
   body{
       background-color:rgb(0, 0, 0);
   }
   .container{
   width: 1080px;
   height: 500px;
   margin-top: 100px;
   margin-left: auto;
   margin-right: auto;
   border-radius: 10px;
   border: 10px solid white;
   background-color:rgb(0, 224, 236);
   }
   h1{
       text-align: center;
       padding-top: 20px;
   }
   .calculate{
       padding-top: 10px;
       padding-bottom: 10px;
       padding-left: 10px;
       padding-right:10px;
       text-align: center;
       font-size: 20px;
   }
   .footer {
 display: block;
 width: 100%;
 height: 40px;
 background-color: rgb(72,0,87);
 text-align: center;
 padding-top: 10px;
 padding-right: 5px;
 margin-right: 15px;
 margin-bottom: 20px;
 color: white;
 margin-top: 150px;
}
</style>
<body>
   <div class="container">
<h1>Area Of Rectangle</h1>   
<form method ="POST">
   {% csrf_token %}
   <div class="calculate"> 
Length=<input type="text" name="length" value="{{l}}"></input></br>
   </div>
   <div class="calculate"> 
Breadth=<input type="text" name="breadth" value="{{b}}"></input></br>
   </div>
   <div class="calculate"> 
<input type="submit" value="calculationarea"></input></br>
   </div>
   <div class="calculate"> 
area=<input type="text" name="area" value="{{area}}"></input></br>
   </div>
   <br>
   <div class="footer">
       Developed by ARSHATHA P
   </div>
</form>
</body>
</html>

VIEWS.PY:

def area(request):
   context = {}
   context["area"] = "0"
   context["l"] = "0"
   context["b"] = "0"
   if request.method == 'POST':
       l= request.POST.get('length','0')
       b= request.POST.get('breadth','0')
       area = int(l) * int(b)
       context["area"] = area
       context["l"] = l
       context["b"] = b
   return render(request,'timetable/area.html',context)

URLS.PY:

from timetable import views

urlpatterns = [
   path('admin/', admin.site.urls),
   path('home/',views.home,name='home'),
   path('area/',views.area,name='area'),
   
]

```



## OUTPUT:
## homepage:
WITHOUT NUMERICAL INPUT:
![OUTPUT](out1.png)
WITH NUMERICAL INPUT:
![OUTPUT](out2.png)


## Result:
Therefor the above codes are successfully executed to run server side programming and do athematical calcualtions and it is published in the following url.
