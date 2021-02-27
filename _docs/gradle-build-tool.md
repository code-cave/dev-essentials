# Gradle Build Tool  
[Gradle](https://gradle.org) is an application build tool. A build tool is very useful for simplifying  
processes that you would run on an application such as compiling the code,  
running tests, packaging the project, importing library packages, and more.  
Gradle is the current build tool of choice for Java projects. [Maven](https://maven.apache.org) is another  
build tool. Even though it's older, it's still widely used because it's so reliable.  
Another build tool is [Ant](https://ant.apache.org). It's older, and rarely used in modern development.  
It's important to learn how to use a build tool well, as doing so will make life  
easier when building applications.

### Content:
- [Installing Gradle](#installing-gradle)
- [Creating A Gradle Project](#creating-a-gradle-project)
- [Gradle Build Config](#gradle-build-config)
- [Running Gradle Tasks](#running-gradle-tasks)

## Installing Gradle
[Installing Gradle](https://gradle.org/install) is pretty easy, there are a few ways to go about it:
- Installing with [SDKMAN!](https://sdkman.io) (recommended):  
  `$ sdk install gradle 6.8.3` (or whichever version is the latest)  
  Installing via SDKMAN! will make it easier to change or update versions.
- Installing with [Homebrew](https://brew.sh) (for Mac only):  
  `$ brew install gradle`
- Installing manually:  
  Gradle can be installed manually as described [here](https://gradle.org/install/#manually).

There are other ways to install, like using a Linux package manager for instance.  
Whichever method used to install, it's normally better to use a package manager.

## Creating A Gradle Project
Creating a project in Gradle is very easy, as IDEs are well integrated with it.  
Each IDE is different, so exact steps won't be described for each, but generally,  
open a new project, select Gradle, then select Java and any additional libraries.  
Once a new Gradle project is created, it should look something like this:

![Gradle Project Structure](../_images/gradle-project-structure.png)

The build.gradle file should be pretty bare, only containing this:
```groovy
plugins {
    id 'java'
}

group 'org.example'
version '1.0-SNAPSHOT'

repositories {
    mavenCentral()
}

dependencies {
    testImplementation 'org.junit.jupiter:junit-jupiter-api:5.6.0'
    testRuntimeOnly 'org.junit.jupiter:junit-jupiter-engine'
}

test {
    useJUnitPlatform()
}
```

Notice the directory gradle/wrapper that was created. The Gradle wrapper is a key  
feature of Gradle in that it's responsible for ensuring that a specific version of Gradle  
is used (the version on the machine that created the project) to run the Gradle tasks.  
This is important for compatibility reasons like when working on an old project that  
had an older version of Gradle, when building, that version of Gradle will be used.

And that's it! A Gradle project was just created, easy peasy.

- [Gradle Build Config](#gradle-build-config)

