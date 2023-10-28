# webshop

hello, I am going to start a project. The project is about implementing the backend of the e-commerce website in Django framework.
I will face with some problems throuogh this way. So I am here to share my firsthand experiences with you :)
Do not forget, I am not an expert backend developer. I am in learning process.


**Issue 1**:
```ruby
django.db.migrations.exceptions.InconsistentMigrationHistory: Migration admin.0001_initial is applied before its dependency account.0001_initial on database 'default'.
```
**Soloution**

Just delete the database and do migration again.
don't forget to backup your data before that.
_________________________________________________________________________________



