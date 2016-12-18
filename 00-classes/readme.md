# Classes and objects

### How to define a class and how to instantiate objects

This is how you would define a class:
```
class Dog {
  String name;
  int age;
  String color;

  // defining our constructor. note the absence of a return type
  public Dog(String name, int age, String color) {
      this.name = name;
      this.age = age;
      this.color = color;
  }

   void barking() {
     System.out.println("woof!");
   }
}

class Main {
  public static void main(String[] args) {
    Dog fido = new Dog("fido", 12, "black");
    Dog dido = new Dog("dido", 10, "white");
    Dog[] dogs = {fido, dido};
    System.out.println(dogs[0].name);
  }
}
```

### Source File Declaration Rules
There can be only one public class per source file. A source file can have multiple non-public classes.
The public class name should be the name of the source file as well which should be appended by .java at the end. For example: the class name is public class Employee{} then the source file should be as Employee.java.

If the class is defined inside a package, then the package statement should be the first statement in the source file.
If import statements are present, then they must be written between the package statement and the class declaration. If there are no package statements, then the import statement should be the first line in the source file.
```
package com.codechallenges;

import java.util.ArrayList;
import java.util.Arrays;

public class AutoCorrect {
  ...
}
```

### What is a java package
In simple words, it is a way of categorizing the classes and interfaces. When developing applications in Java, hundreds of classes and interfaces will be written, therefore categorizing these classes is a must as well as makes life much easier.

### Modifiers
Modifiers are keywords that you add to those definitions to change their meanings. Java language has a wide variety of modifiers:
* Access modifiers
  * Visible to the package, the default. No modifiers are needed.
  * Visible to the class only (`private`).
  * Visible to the world (`public`).
  * Visible to the package and all subclasses (`protected`).

* Non-access modifiers
  * The `static` modifier for creating class methods and variables.
  * The `final` modifier for finalizing the implementations of classes, methods, and variables.
  * The `abstract` modifier for creating abstract classes and methods.
  * The `synchronized` and `volatile` modifiers, which are used for threads.

To use a modifier, you include its keyword in the definition of a class, method, or variable. The modifier precedes the rest of the statement, as in the following example (using public, private, static, final, protected):
```
public class className {
   // ...
}


private boolean myFlag;
static final double weeks = 9.5;
protected static final int BOXWIDTH = 42;

public static void main(String[] arguments) {
   // body of method
}
```
