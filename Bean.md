Beans are the fundamental building blocks of a [[Spring]] application and represent the various [[Component]] and objects that make up the application.

To define a [[bean]] in [[Spring]], you typically annotate a class with the `@Component` or one of its specialized [[Annotation]] such as `@Service`, `@Repository`, or `@Controller`. These [[Annotation]] indicate that the class should be treated as a bean and managed by the [[Inversion of Control|Spring container]].

Once a class is annotated as a bean, it can be instantiated and used within the application by obtaining a reference to it from the [[Inversion of Control|Spring container]]. This is usually done using [[dependency injection]], where the container automatically injects the [[Dependencies]] into the bean.

[[Simple Bean Example]]

#Spring 