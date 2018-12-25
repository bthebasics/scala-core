### Gradle Project Structure

- **setting.gradle**

  specifies the root project and modules to be included

  ```groovy
  rootProject.name = 'java-project'
  include 'json-display'
  ```

- **build.gradle**

```groovy
// shows artifact information
group 'info.garagesalesapp'
version '1.0-SNAPSHOT'

// to make java-aware to say this is java project
apply plugin: 'java'

// version compatibility
project.sourceCompatibility = 1.8

// repositories 
repositories {
    mavenCentral()
}

//external dependencies
dependencies {
    testCompile group: 'junit', name: 'junit', version: '4.12'
    compile 'com.google.code.gson:gson:2.8.0'
    compile project(':json-display')
}

// additional plugin
apply plugin: 'project-report'

// you can customize the default properties
//project.buildDir = "mybuildDir"
```



- **Source directory**

  will hold the source code and additional files

  ​	**main** --> will hold the code and modules

  ​	**test**  --> all the relevant unit test code will be sent



- **wrapper files**

  gradlew.bat provides lightweight wrapper around gradle; 

  Its thin layer around gradle , Checks to see if the requested version of gradle installed 

  Passes the command onto the real Gradle

  in the gradle directory - there is java program which will run and install the version of gradle from the properties file


- **build directory**

  output of the build command ; stores compilation outputs 

  **libs** will store the final FAT jar

  **gradle clean** will clean/remove the build directory


- .idea files - metadata from intelliJ
