# NOTES

The most important person you will ever have to communicate with is your future self.

**Object** is a collection of data and associated behaviors.

**Object-oriented analysis (OOA)** is the process of looking at a problem, system,
or task (that somebody wants to turn into a working software application) and
identifying the objects and interactions between those objects.

**Object-oriented design (OOD)** is the process of converting requirements
into an implementation specification. The designer must name the objects, define
the behaviors, and formally specify which objects can activate specific behaviors
on other objects. The design stage is all about transforming what should be done
into how it should be done.

**Object-oriented programming (OOP)** is the process of converting a design into a
working program that does what the product owner originally requested.

**Members** or **properties** - are class attributes.

**Behaviors** are actions that can occur on an object. The behaviors that can be performed on a specific class of object are expressed as the methods of the class.

**Interface** - the key purpose of modeling an object in object-oriented design is to determine what the public interface of that object will be. The interface is the collection of attributes
and methods that other objects can access to interact with that object. Other objects
do not need, and in some languages are not allowed, to access the internal workings
of the object. Always design the interface of an object based on how easy
it is to use, not how hard it is to code (this advice applies to user interfaces as well). When designing the interface, imagine you are the object; you want clear definitions
of your responsibility and you have a very strong preference for privacy to meet
those responsibilities. Don't let other objects have access to data about you unless
you feel it is in your best interest for them to have it. Don't give them an interface
to force you to perform a specific task unless you are certain it's your responsibility
to do that.

- variables with a leading _ in their name as a warning that these aren't part of the public interface.

**Encapsulation** - the  process of hiding the implementation of an object. Encapsulated data is not necessarily hidden. Encapsulation is, literally, creating a capsule (or wrapper) on the attributes

**Composition** - is the act of collecting several objects together to create a new one.

**Abstract methods** -  basically say this:

- "We demand this method exist in any non-abstract subclass, but we are declining to
specify an implementation in this class."

**Polymorphism** is the ability to treat a class differently, depending on which subclass is implemented. In python it is a duck typing:

- if it walks like a duck or swims like a duck, we call it a duck.

**MRO - Method Resolution Order** - help us understand which of the alternative methods will be used.

**4+1 Views**. The views are:

- A logical view of the data entities, their static attributes, and their
relationships. This is the heart of object-oriented design.

- A process view that describes how the data is processed. This can take a
variety of forms, including state models, activity diagrams, and sequence
diagrams.

- A development view of the code components to be built. This diagram
shows relationships among software components. This is used to show how
class definitions are gathered into modules and packages.

- A physical view of the application to be integrated and deployed. In cases
where an application follows a common design pattern, a sophisticated
diagram isn't necessary. In other cases, a diagram is essential to show how a
collection of components are integrated and deployed.

- A context view that provides a unifying context for the other four views.
The context view will often describe the actors that use (or interact) with
the system to be built. This can involve human actors as well as automated
interfaces: both are outside the system, and the system must respond to these
external actors.

The mypy tool is commonly used to check the hints for consistency.

**Modules** are Python files, nothing more. The single file in our small program is a module.

A **package** is a collection of modules in a folder. The name of the package is the name of the folder.

**dunder** - Double underscore __


src/  
+-- main.py  
+-- ecommerce/  
+-- __init__.py  
+-- database.py
+-- products.py  
+-- payments/  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+-- __init__.py      
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+-- common.py  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+-- square.py  
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+-- stripe.py  
+-- contact/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; +-- __init__.py  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+-- email.py

wrap all your scripts in an if __name__ == "__main__": test, just in case you write a
function that you may want to be imported by other code at some point in the future. put startup code in a function (conventionally, called main()) and only execute that function when we know we are running the module as a script, but not when our code is being imported from a different script. We can do this by guarding the call to main inside a conditional statement, demonstrated as follows:

```python
...
def main() -> None:
    """
    Does the useful work.
    >>> main()
    p1.calculate_distance(p2)=5.0
    """
    p1 = Point()
    p2 = Point(3, 4)
    print(f"{p1.calculate_distance(p2)=}")

if __name__ == "__main__":
    main()
...
```

"We're all adults here." There's no need to declare a variable as private when we can all see the source code.

**Inheritance** - include the name of the parent class inside parentheses between the class name and the colon that follows. This is all we have to do to tell Python that the new class should be derived from
the given superclass.

```python
class MySubClass(object):
    pass
```

**super()** function does returns the object as if it was actually an instance of the parent class, allowing us to call the parent method directly.

**Multiple inheritance** - include inside the class definition parentheses,  two (or more) clasees,
separated by a comma.

```python
class EmailableContact(Contact, MailSender):
    pass
```

**The special parameter /**  separates parameters that could be
provided by position in the call from parameters that require a keyword to associate
them with an argument value. We've given all string parameters an empty string as a
default value, also.

**\*\*kwargs** syntax, it basically collects
any keyword arguments passed into the method that were not
explicitly listed in the parameter list. These arguments are stored
in a dictionary named kwargs (we can call the variable whatever
we like, but convention suggests kw or kwargs). When we call a
method, for example, super().__init__(), with **kwargs as an
argument value, it unpacks the dictionary and passes the results
to the method as keyword arguments

**\# type** ignore comments provide a specific error
code, call-arg, on a specific line to be ignored.

```python
# this case, we need to ignore the super().__init__(**kwargs) calls because it isn't obvious to mypy what the MRO really will be at runtime.
super().__init__(**kwargs) # type: ignore [call-arg]
```

**Docstrings** - when writing docstrings, don't explain how the code works (the code should do
that). Be sure to focus on what the code's purpose is, what the preconditions are for
using it, and what will be true after the function or method has been used.

**Design notes** notes

- small circle (or a "+" to save space) as a prefix - depicts The public attributes.
- small square (or sometimes a "-") - depicts private attributes

**Design principles**:
- DRY - Don't repeat yourself

**The type object** - is called the metaclass, the class used to build classes. This means
every class object is an instance of type.

**The lonely \*** separates parameters where the argument value
can be provided positionally from parameters where the argument value must be
provided as a keyword. ```def __init__(self, *, training_subset: float = 0.80) -> None:```

[text](https://archive.ics.uci.edu/dataset/53/iris)
