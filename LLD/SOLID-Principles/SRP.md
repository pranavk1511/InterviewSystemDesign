# SOLID Principle 

-  Single Responsiblity 
This principle means that the class has only one reason to change i.e one responsilblity . The whole idea is to reduce the complexity of the application and break it down into smaller , more readable components 

- How to implement ? 
    - <b>Identify Responsiblities</b> : Identify all the reasons a class might want to change . eg. Data to db send a response etc . 
    - <b>Distribute Responsiblities </b> : Once you have identified all the responsiblities try implementing different classes for each repsponsiblity 
    - <b> Focus On Abstraction </b> :Create abstractions that separate the concerns effectively. Each class should represent a single abstraction.

- Here is how you implement SRP 

```python
class User:
    def __init__(self, name, email):
        self.name = name
        self.email = email

    def save_to_database(self):
        print(f"Saving {self.name} to database")

    def send_email(self, message):
        print(f"Sending email to {self.email}: {message}")
```

A single class contains two functions save_to_database  and send_email . It has three responsiblities in total : 

1. Manage data spoints  
2. save the name to database and
3. send an email. 

After applying SRP , the new structure is as follows
```python
class User:
    def __init__(self, name, email):
        self.name = name
        self.email = email

class UserRepository:
    def save(self, user):
        print(f"Saving {user.name} to database")

class EmailService:
    def send_email(self, user, message):
        print(f"Sending email to {user.email}: {message}")
```
