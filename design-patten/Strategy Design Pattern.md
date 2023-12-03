The Strategy Design Pattern is [[behavioral design patten]] that allows you to define a family of algorithm, encapsulation each of them, and make them interchangeable. The pattern lets you choose the appropriate algorithm to use at runtime. It's particularly useful when you have multiple ways to do a particular task and want decouple the client from the implementation detail of that algorithm.

```Java
// Step 1: Define the Strategy Interface
interface PaymentStrategy {
    void pay(int amount);
}

// Step 2: Create Concrete Strategies
class CreditCardPayment implements PaymentStrategy {
    private String cardNumber;
    private String name;

    public CreditCardPayment(String cardNumber, String name) {
        this.cardNumber = cardNumber;
        this.name = name;
    }

    @Override
    public void pay(int amount) {
        System.out.println("Paid " + amount + " dollars using credit card: " + cardNumber);
    }
}

class PayPalPayment implements PaymentStrategy {
    private String email;

    public PayPalPayment(String email) {
        this.email = email;
    }

    @Override
    public void pay(int amount) {
        System.out.println("Paid " + amount + " dollars using PayPal with email: " + email);
    }
}

// Step 3: Create the Context
class ShoppingCart {
    private PaymentStrategy paymentStrategy;

    public void setPaymentStrategy(PaymentStrategy paymentStrategy) {
        this.paymentStrategy = paymentStrategy;
    }

    public void checkout(int totalAmount) {
        paymentStrategy.pay(totalAmount);
    }
}

// Step 4: Client Code
public class Main {
    public static void main(String[] args) {
        ShoppingCart cart = new ShoppingCart();

        // Pay with a credit card
        PaymentStrategy creditCard = 
	        new CreditCardPayment("1234-5678-9876-5432", "John Doe");
        cart.setPaymentStrategy(creditCard);
        cart.checkout(100);

        // Pay with PayPal
        PaymentStrategy payPal = new PayPalPayment("john.doe@example.com");
        cart.setPaymentStrategy(payPal);
        cart.checkout(50);
    }
}
```

For the above example:
- the `PaymentStrategy` interface defines the contract for the payment strategies.
- the `CreditCardPayment` and `PayPalPayment` are two concreate strategies implementing the payment algorithms.
- The `ShoppingCart` class is the context that can be configured with a payment strategy.

#design-pattern 