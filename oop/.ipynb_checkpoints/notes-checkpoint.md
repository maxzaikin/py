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
