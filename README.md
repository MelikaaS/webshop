# webshop

hello, I am going to start a project. The project is about implementing the backend of the e-commerce website in Django framework.
I will face with some problems throuogh this way. So I am here to share my firsthand experiences with you and also as reminder for myself :)
Do not forget, I am not an expert backend developer. I am in learning process.


**Issue 1**:
```ruby
django.db.migrations.exceptions.InconsistentMigrationHistory: Migration admin.0001_initial is applied before its dependency account.0001_initial on database 'default'.
```
**Soloution**

Just delete the database and do migration again.
don't forget to backup your data before that.
_________
**Issue 2**
```ruby
Error: That port is already in use.
```
I faced with this problem when I was going to run runserver command.
I work on Ubuntu 22.04.

**Soloution**
based on [https://stackoverflow.com/questions/20239232/django-server-error-port-is-already-in-use]
you should just write the below comand to kill all the processes associated with port 8000. 
```ruby
sudo fuser -k 8000/tcp
```

and for more extra info : *TCP Port 8000 is commonly used for development environments of web server software.*
___________
or by using below commands find pycharm process and kill it.
```ruby
ps -ef | grep -i pycharm  | grep -v grep
```

```ruby
kill -9 ProcessID
```
-9 option means forced termination.

__________
some useful information about **POST** and **GET**
_____
**GET** and **POST** are the only HTTP methods to use when dealing with forms.

Django’s login form is returned using the **POST** method, in which the browser bundles up the form data, encodes it for transmission, sends it to the server, and then receives back its response.
use **POST** for any request that could be used to change the state of the system - for example, a request that makes changes in the database.

**GET** bundles the submitted data into a string, and uses this to compose a URL. The URL contains the address where the data must be sent, as well as the data keys and values. 
**GET** should be used only for requests that do not affect the state of the system.

**POST** method is useful for :  
Login and password form because of CSRF protection that offers more control over access.

**GET** method is useful for :  
large quantities of data, or for binary data, such as an image.
a web search form

______
**Issue3**:
```ruby
Exception Value:	
'WSGIRequest' object has no attribute 'get'
```
**The reason of error:**
```ruby
def login(request):
    form = forms.LoginForm(request)
    if request.method == 'POST':
    ...
   
    return render(request,"account/login.html", context={'form': form, 'message': message})
```
**Solution:**
```ruby
def login(request):
    form = forms.LoginForm()
    if request.method == 'POST':
    ...
   
    return render(request,"account/login.html", context={'form': form, 'message': message})
```
______
**Issue4**:
what is UUID?
UUID(Universal Unique Identifier) is a Python library that generates random objects of 128 bits.
