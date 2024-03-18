# Liskovs Substitution 

This principle states that `If class B is subtype of Class A , then we should be able to replace object of A with object of B without breaking the previous behaviour ` . The child class should extend the capablity of the parent class and should not narrow it down . 

```python 
class Bird:
    def fly(self):
        return "Flying"

class Eagle(Bird):
    def fly(self):
        return "Eagle flying high"

class Ostrich(Bird):
    def fly(self):
        raise Exception("Ostrich cannot fly")

```
In this example, the Ostrich class violates LSP because it changes the behavior of the fly method by raising an exception, whereas other Bird types like Eagle can fly. This means Ostrich is not a substitutable subclass for Bird with respect to the fly method.

To adhere to LSP, we should redesign the class hierarchy to ensure that all subclasses of Bird can indeed perform the fly action, or we should not assume that all birds can fly:

```python
class Bird:
    pass

class FlyingBird(Bird):
    def fly(self):
        return "Flying"

class Eagle(FlyingBird):
    def fly(self):
        return "Eagle flying high"

class Ostrich(Bird):
    pass

```
