# Android - Recompile with "-Xlint:deprecation" and/or "-Xlint:unchecked" flag

After building an app, Gradle throws a warning indicating that some files are using or overriding a deprecated API, or that they are using unchecked or unsafe operations.

Unfortunately, the compiler doesn't tell you which files are affected. To get more details about the warning:

* Use the "-Xlint:unchecked" flag to get more info on unchecked/unsafe operations
* Use the "-Xlint:deprecation" flag to get more info on deprecated usage

This goes in your build.gradle file inside the `allprojects{}` section.
You can append multiple arguments by using `<< "-argument"`:

~~~
gradle.projectsEvaluated{
        tasks.withType(JavaCompile){
            options.compilerArgs << "-Xlint:unchecked" << "-Xlint:deprecation"
        }
    }
~~~~
