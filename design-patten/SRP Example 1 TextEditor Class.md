Suppose we are working with a `TextEditor` class in Java that violates the [[Single Responsibility Principle|SRP]]:

```Java
public class TextEditor {
    public void openFile(String fileName) {
        // Code to open a file
    }

    public void saveFile(String fileName) {
        // Code to save a file
    }

    public void spellCheck(String text) {
        // Code to perform spell-checking
    }

    public void formatDocument(String text) {
        // Code to format the document
    }

    public void printDocument(String text) {
        // Code to print the document
    }
}
```

To adhere to the [[Single Responsibility Principle|SRP]], we can split the responsibilities into separate classes:

```Java
public class FileHandler {
    public void openFile(String fileName) {
        // Code to open a file
    }

    public void saveFile(String fileName) {
        // Code to save a file
    }
}

public class SpellChecker {
    public void spellCheck(String text) {
        // Code to perform spell-checking
    }
}

public class TextFormatter {
    public void formatDocument(String text) {
        // Code to format the document
    }
}
```

Now, each class has a single responsibility, making the code more maintainable.

#design-pattern #SOLID 