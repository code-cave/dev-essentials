# Java Object Oriented Programming (OOP) Language  
Java is one of the most major languages in backend enterprise systems.  
It's an object oriented language with strong typing and class hierarchy.  
It's been around since the 90's so Java has had plenty of time to mature  
and have frameworks and support be built around it. Java arguably has  
more packages and frameworks built around it than any other language.

### Content:
- [Installing Java](#installing-java)
- [Learn Vanilla Java](#learn-vanilla-java)
- [Debugging Java](#debugging-java)
- [Write JUnit Tests](#write-junit-tests)

## Installing Java
Java is already installed on Mac machines, but usually it's just JDK 8.  
The latest LTS version of Java (currently JDK 11) should be installed.  
The AdoptOpenJKD distribution of Java JDK 11 is preferred because  
it's open source, and let's face it, Oracle is dumb.

The dowload and install can be done directly via package installer from  
[AdoptOpenJDK](https://adoptopenjdk.net/) or via the [SDKMAN!](https://sdkman.io/install) Software Development Kit manager.  
The AdoptOpenJDK package installer is the simplistic way to install Java  
whereas using SDKMAN provides a package manager to install different  
versions of Java, making updating or changing JDK versions much easier.  
Either way of installing is fine, SDKMAN! is just for the more hardcore Java  
developer who wants to easily be able to change JDKs because of working  
on different projects that use different JDK versions.

Once Java is installed, open a new shell and verify the Java version:  
```
$ java -version
openjdk version "11.0.7" 2020-04-14
OpenJDK Runtime Environment AdoptOpenJDK (build 11.0.7+10)
OpenJDK 64-Bit Server VM AdoptOpenJDK (build 11.0.7+10, mixed mode)
```
Now the Java coding may commence!

## Learn Vanilla Java
Learning vanilla Java entails writing Java classes using only packages  
included in the JDK, compiling the classes, and then running the program  
by using the `java` command. Java is a compiled language, that means it  
must always be compiled in order to run.

**Learn the basics:**
- Write the classic "Hello World!" program, compile it, and run it.
- Understand what the Main class and main method are/do
- Learn about the primitive types and object types
- Learn about Java class structure:
  - Class fields
  - Public, private, package, and protected access modifiers
  - Class constructor(s)
  - Normal class methods
  - Static fields and methods
  - Getter and setter methods for class fields
- Learn about Java package structure  
  Note: the project structure is normally src/main/java and underneath  
  java is where the containing package is. By convention, it's usually  
  com.companyname.applicationname which would correspond to the  
  directory src/main/java/com/companyname/applicationname.
- Learn about subclasses (child classes) and inheritance
- Write the classic Employee program  
  Note: Java programs with multiple classes should be compiled  
  into a folder **bin** under the project root. Do this by running:  
  `javac -d bin -sourcepath src/main/java src/main/java/path/to/Main.java`  
  The program is run by:  
  `java -cp bin path/to/Main`  
  The program can also be compiled and run by the IDE.
- Learn about interfaces and implementing them

## Debugging Java
Using a debugger is the best way to see what's happening inside Java code  
when it runs, but doesn't produce the expected results. The IDE debugger  
should be used, since it is the simplest. Just add in break point(s) to  
lines of code to investigate and run the program in debug mode in the IDE.

**Become familiar with basic debugger functions:**
- Step over
- Step into
- Step out
- Resume program

Debugging is usually fairly simple in Java and is invaluable.  
Make sure to look at the objects and variables in the debugger  
and understand how to expand them to see values and investigate.  
That's about all there really is to debugging in Java, easy peasy.

## Write JUnit Tests
Writing unit tests for Java code is necessary, it makes sure that what's  
expected to happen in the code does, in fact, happen. There is also the  
matter of code coverage with respect to writing unit tests. Java projects  
are considered adequately covered if the unit test coverage is above 95%.  
Typically, unit tests should be written to cover specific cases in the code  
that cover certain conditions. Many small, manageable unit tests are better  
than few very large unit tests. Ideally, unit tests should be as short, sweet,  
and easy to understand as possible.

JUnit is the basic built in Java unit testing framework, it gets the job done.  
There are many other testing frameworks for Java that provide better ways of  
going about unit tests to make them shorter to write or mock certain behaviors,  
but since this stuff is more or less introductory, and vanilla Java is being used,  
learning JUnit will suffice. Every Java developer should know JUnit anyways.

**Write unit tests for the Employee program:**
- Make a unit test file for each class.  
  Note: Java unit test classes are named the same as the corresponding  
  class name, but with **Test** appended. Unit test files should go in a folder  
  called **test** underneath the src folder, and the package structure for each  
  test class should be the same as the structure for the corresponding class.
- Make a unit test for each method in each class.
- Use the IDE or command line to run the JUnit tests.
- Use the IDE to check the test coverage, and make sure it is above 95%.

There is plenty of information about doing these things online.

