- [[Dependency]]: A dependency is an object or service that a class relies on to perform its operations. It could be another class, database connection, network service, or any other external resource.
  
- Dependent Class: The class that requires one or more [[Dependencies]] to perform its functionality is called the dependent class.

- Dependency Provider/Container: The external entity responsible for managing and providing the dependencies to the dependent classes is known as the dependency provider or container. It handles the instantiation and lifecycle management of the [[Dependencies]].
  
- Types of Dependency Injection: 
	- Constructor Injection: [[Dependencies]] are provided to the dependent class through its constructor. This is the most common and preferred form of DI. 
	
	 - Setter Injection: [[Dependencies]] are set on the dependent class through setter methods. 
	
	 - Interface Injection: The dependent class implements an interface that defines methods to inject [[Dependencies]].

#Spring 