# About this Package

This package provides a gradle build file (`build.gradle`) along with a
[gradle wrapper](http://www.gradle.org/docs/current/userguide/gradle_wrapper.html).
It is intended to ease a quick start with [gradle](http://www.gradle.org)
in the context of Java, Eclipse, and Tomcat.

# General Usage

1. Download gradle-package from https://github.com/koppor/gradlepackage/archive/master.zip

2. Extract it in source directory

3. Adapt build.gradle if source path is not `src/main/java`

4. Running
 * Run `gradlew eclipse` to update eclipse dependencies
 * Run `gradlew war` to create a war
 * Run `gradlew tasks` to list all available tasks
 * Run `gradlew dependencyUpdates` to display a report of the project dependencies


# Using Sonar

[Sonar](http://www.sonarsource.org/) is a tool to monitor the code quality of your Java projects

1. Download Sonar 3.5.1 from http://www.sonarsource.org/downloads/

2. Extract it

3. Go into sonar-3.5.1\bin\windows-x86-32 and run StartSonar.bat

4. Open command line in your folder

5. Run `gradlew sonarRunner`
wait until it is complete

6. Open http://localhost:9000/dashboard/index/1
You should see the statistics

A click on [Critical](http://localhost:9000/drilldown/violations/1?severity=CRITICAL)
(upper right corner) brings you to critical style violations.


#Tuning the Eclipse Setup
The files `.classpath`, `.project`, and `.settings/org.eclipse.jdt.core.prefs`
are contained in `.gitignore` as they are generated by gradle. In case you
add custom configuration, which cannot be generated by gradle, remove the file from
`.gitignore` and add it to the version control. When running `gradlew eclipse`, gradle
will merge its changes into the existing file. Run `gradlew eclipse` before committing the
change: gradle has a different oppinion on closing XML elements than eclipse.