#### Dependencies Management

1.  Declaring the dependencies and repositories

```groovy
dependencies {
    compile 'com.google.code.gson:gson:2.8.0'
    compile 'org.apache.spark:spark-sql_2.11:2.1.0'
    }
```

1. Including the Dependency reports

   ```groovy
   apply plugin: 'project-report' 
   ```

   **gradle dependency**

2. Saving reports in HTML

   run command 
   **gradle htmlDependencyReport**



   #### Creating libraries and putting the dependencies

   - Create module <module-json-display>   inside <java-project> main module
   - This will create sub-directory <json-display> inside <java-project> with its own build.gradle
   - settings.gradle will show below on project level should show below 

   ```groovy
   rootProject.name = 'java-project'
   include 'json-display'
   ```

   - to resolve the dependency in <java-project> to have <json-display> 

     update build.gradle to have as 

     ```groovy
     project.dependencies {
         testCompile group: 'junit', name: 'junit', version: '4.12'
       //  compile 'com.google.code.gson:gson:2.8.0'
         compile project(':json-display')  // this will cause json-display module to be included 
     }
     ```


