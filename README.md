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
