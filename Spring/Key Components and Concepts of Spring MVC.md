1. DispatcherServlet: The DispatcherServlet is the entry point of a [[Spring MVC]] application. It intercepts incoming HTTP [[Request|requests]] and routes them to the appropriate [[Controllers|controller]] based on the URL mapping.
    
2. [[Controllers]]: Controllers are Java classes that handle the incoming [[Request|requests]] and process the [[Business Logic]]. They are responsible for interacting with the [[Model|model]] and selecting the [[Views and Templates|View]] to render the [[Response]].
    
3. Views: [[Views are templates]] or presentation files that define the structure and layout of the user interface. [[Spring MVC]] supports various view technologies, including [[JSP]], [[Thymeleaf]], and [[FreeMarker]].
    
4. [[Model]]: The Model represents the data and [[Business Logic]] of the application. It holds the application's state and provides methods to access and manipulate the data.
    
5. Handler Mapping: Handler mapping is responsible for mapping incoming [[Request|requests]] to the appropriate [[Controllers|controller]] based on the URL pattern.
    
6. View Resolver: The View Resolver is responsible for resolving the view name returned by the controller to the actual View template that will be rendered.
    
7. Data Binding: [[Spring MVC]] provides data binding support to map incoming request parameters to Java objects and vice versa. This simplifies form handling and data processing.
    
8. Interceptors: Interceptors allow you to intercept and pre-post-process [[Request|requests]] and responses. They can be used for tasks like [[authentication]], [[logging]], and [[auditing]].

#SpringMVC #Spring 