Refers to the process of establishing the relationships and [[Dependencies]] between various [[Component]] in an application. It involves connecting different parts of the application to enable them to work together seamlessly.

In [[Spring]], there are three main approaches to wiring components:

- XML-based configuration : In the traditional approach, [[Component Wiring]] is defined in XML configuration files. XML elements, such as `<bean>`, are used to define the [[Bean]] ([[Component]]) and their dependencies. The configuration file specifies how the [[Bean]] are instantiated, their properties set, and their relationships established.

- Annotation-based configuration : With the rise of Java [[Annotation]], Spring introduced support for annotation-based configuration. [[Annotation]], such as `@Component`, `@Autowired`, and `@Qualifier`, are used to mark classes as [[Component]], specify [[Dependencies]], and resolve conflicts. [[Spring]] automatically scans the [[Classpath]] for annotated [[Component]] and performs the [[Component Wiring]] based on the specified [[Annotation]].

- Java-based configuration : Java-based configuration allows [[Component Wiring]] using plain Java code. Configuration classes are written in Java and annotated with `@Configuration`. Beans and their relationships are defined using `@Bean` annotations. Java-based configuration provides a more type-safe and programmatic approach to wiring components.

#Spring 