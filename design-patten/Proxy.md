**What is the Proxy Pattern?**

The Proxy pattern provides a surrogate or **intermediate object** that acts on behalf of another object. It controls access to the real object, adding additional functionalities or modifying its behavior without altering the original object itself.

**Why use the Proxy Pattern?**

- **Encapsulation and security:** Hide the implementation details of the real object and control access to its sensitive resources.
- **Performance optimization:** Cache frequently accessed data or expensive operations performed by the real object.
- **Lazy initialization:** Delay the creation of the real object until it is actually needed, improving resource efficiency.
- **Logging and monitoring:** Intercept calls to the real object to log activity or perform additional processing.

**When to use the Proxy Pattern?**

- **Remote access:** Create a local proxy for a remote object to handle network communication and latency.
- **Expensive object creation:** Use a proxy to delay the creation of a resource-intensive object until absolutely necessary.
- **Controlled access:** Limit access to a sensitive object based on certain conditions or permissions.
- **Extending functionality:** Add additional functionalities to an existing object without modifying its original code.

**Where to use the Proxy Pattern?**

- **Database access:** Implement a proxy for database connections to manage pooling, caching, and security checks.
- **Network communication:** Use a proxy server to filter traffic, control bandwidth, and perform caching.
- **File access:** Create a proxy for file access to handle caching, security checks, and access control.
- **Remote object invocation:** Implement a local proxy for remote objects to handle network communication and serialization.

**How to implement the Proxy Pattern in Java:**

Here's a basic example of a proxy for a file access operation:

**1. Define the Subject interface:**

```Java
public interface FileAccess {
    byte[] read(String filename);
    void write(String filename, byte[] data);
}
```

**2. Implement the Real Subject class:**

```Java
public class FileAccessImpl implements FileAccess {
    @Override
    public byte[] read(String filename) {
        // Read data from file
        // ...
        return data;
    }

    @Override
    public void write(String filename, byte[] data) {
        // Write data to file
        // ...
    }
}
```

**3. Implement the Proxy class:**

```Java
public class FileAccessProxy implements FileAccess {
    private FileAccess realSubject;

    public FileAccessProxy(FileAccess realSubject) {
        this.realSubject = realSubject;
    }

    @Override
    public byte[] read(String filename) {
        // Check cache for previously accessed files
        byte[] data = // Get data from cache if available
        if (data == null) {
            data = realSubject.read(filename);
            // Add data to cache for future access
        }
        return data;
    }

    @Override
    public void write(String filename, byte[] data) {
        // Perform additional validation or logging before writing
        realSubject.write(filename, data);
    }
}
```

**Client usage:**

```Java
FileAccess proxy = new FileAccessProxy(new FileAccessImpl());

byte[] data = proxy.read("myfile.txt");
proxy.write("newfile.txt", data);
```

This example demonstrates how a proxy can intercept file access operations, perform caching for performance optimization, and add additional validation or logging before writing to the file.

**Remember:**

- Define a clear interface for the real subject and proxy.
- Implement the desired functionalities within the proxy class.
- Delegate calls to the real subject when necessary.
- Choose the appropriate type of proxy (virtual, remote, etc.) based on your specific needs.

#design-pattern #structural-pattern