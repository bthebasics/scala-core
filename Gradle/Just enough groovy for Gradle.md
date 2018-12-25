#### Just enough groovy for Gradle

below snippets show how to use groovy in concise way .

```groovy
// Just enough groovy for gradle
System.out.println("Hello world");

println("Hello world")

println "Hello world"

// another exaple
// below example takes code at run time using closures

class MyClass {
    void  doSomething(Closure closure) {
        closure.call()
    }
}

myobject = new MyClass()

myobject.doSomething {
    println new Date()

}

// you can customize the default properties
project.buildDir = "mybuildDir"
```



#### Gradle POM ( Project Object Model )

is java object build by gradle when we run build.gradle. It represents the "things" in our application. 

Gradle uses it to build our applications.



1. The most important in POM is project object itself. It has one to one with build.gradle
2. Assigned to reference variable "project"

```groovy
// you can prefix project variable as below and its still is valid
project.sourceCompatibility = 1.8

repositories {
    mavenCentral()
}

project.dependencies {
    testCompile group: 'junit', name: 'junit', version: '4.12'
    compile 'com.google.code.gson:gson:2.8.0'
}
```



##### task

1. Project is collection of tasks
2. Tasks are collection of actions
3. Actions are actual function performed by Gradle
4. Actions lists tasks for project

```groovy
// you can customize the default properties
project.buildDir = "mybuildDir"
```



#### Dependencies Management





