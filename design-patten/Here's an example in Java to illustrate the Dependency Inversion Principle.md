```Java
// High-level module (business logic)
class CustomerService {
    private CustomerRepository customerRepository;

    public CustomerService(CustomerRepository customerRepository) {
        this.customerRepository = customerRepository;
    }

    public void addCustomer(Customer customer) {
        customerRepository.save(customer);
    }
}

// Low-level module (data access)
class CustomerRepository {
    public void save(Customer customer) {
        // Code to save the customer to the database.
    }
}

class Customer {
    private String name;
    
    public Customer(String name) {
        this.name = name;
    }
}
```

In the example above, the `CustomerService` high-level module depends directly on the `CustomerRepository` low-level module. This violates the Dependency Inversion Principle.

To adhere to the DIP, we can introduce an interface (`CustomerRepositoryInterface`) to abstract the data access layer:

```Java
interface CustomerRepositoryInterface {
    void save(Customer customer);
}

// High-level module (business logic)
class CustomerService {
    private CustomerRepositoryInterface customerRepository;

    public CustomerService(CustomerRepositoryInterface customerRepository) {
        this.customerRepository = customerRepository;
    }

    public void addCustomer(Customer customer) {
        customerRepository.save(customer);
    }
}

// Low-level module (data access)
class DatabaseCustomerRepository implements CustomerRepositoryInterface {
    public void save(Customer customer) {
        // Code to save the customer to the database.
    }
}
```

Now, the high-level module (`CustomerService`) depends on the abstraction (`CustomerRepositoryInterface`), and the low-level module (`DatabaseCustomerRepository`) implements the details. This design adheres to the Dependency Inversion Principle, allowing you to swap out different implementations of `CustomerRepositoryInterface` without changing the high-level module. It promotes flexibility and maintainability in the codebase.

#design-pattern 