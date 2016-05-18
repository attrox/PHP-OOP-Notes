SOLID Principles:
Single Responsibility
	A class should only have 1 and only 1 reason to change.
	TELL DON’T ASK! Push un-related responsibility to an interface that make sense to handle it. Use the interface’s method in the code and let the implementation of the interface’s method handled somewhere else.

Open-Closed principle 
	Open for extension, Closed for Modification. Create a common interface, flip the dependency by coding to the interface. You just need to create a class implementing the interface and you don’t need to change the original code.

Liskov Substitution
	Child class should be substitutable with the Parent class. Meaning the extended methods of the Child classes shouldn’t have a different return types or exit point. Eg: Parent’s method does not throw an exception but the Child method throw an exception (totally different behavior of the methods), parent and child method return different types so the consumer of the class need to do an if/else to check the return type.

Interface Segregation
	Create multiple interfaces with single responsibility. Concrete class implements only the interface that it needs.

Dependency Inversion, use interface as dependency injection and code to the interface.


Design Patterns:
Use Decorator instead of inheritance to add or adjust behaviors.
	This way you don’t need to encapsulate all the functionalities. 
	Basic object implementing an interface. Other object also implementing the interface but behave as a decorator of the basic object. 
	It wraps the basic object and add functionalities to it.

 Adapter
	To allow an object that only uses the old interface to be able to consume the new interface.
	Create a class that will ADAPT (implement) the old interface and inject the new interface via constructor.

Template Method
	Create abstract class that has re-useable methods (inside it calls a declared abstract method to be implemented by the child’s class). The abstract method is the different behavior to be implemented by the child but the rest are re-useable as a template. 

Chain of Responsibility
	Need to perform different tasks in succession but each tasks has the ability to stop the process.
	Has an abstract class that can keep track the successor and an implemented next() method that call an abstract method that will be implemented by the child class.

Strategy pattern
	Create a class that will consume an object that we want to modify some certain behavior. The object class code itself does not need to be modified but the Strategy class handles the modification of the behavior.


Additional Notes:

Do not swallow exceptions

Resist the urge to handle exceptions immediately.

In general libraries should be more conservative with catching exceptions whereas at the top level of your program (e.g. in your main method or in the top of the action method in a controller, etc) you can be more liberal with what you catch.

Don't catch exceptions when you don't want to. Just don't. Instead, let them trickle up the call tree until either you have a good solution or you hit the main function, in which case you can be sure that error information is correctly routed.

Never try to implement a catch-all handler for the base exception type. Rescuing or catching all exceptions wholesale is never a good idea