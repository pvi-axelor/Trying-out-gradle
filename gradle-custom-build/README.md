## Custom built gradle java project

This dir structure wasn't generated using gradle basic, it was manually build.

It simply contains four files:

> src
>> main
>>> java
>>>> package
>>>>> Main-class

> build.gradle 

> build-auto-jar.gradle 

> build-runnable-jar-with-run-task.gradle 

It can be built by running ```gradle build``` command.

It can be run using ```java -cp build/libs/gradle-custom-build-0.0.1_inital_phase.jar trying.apackage.basic.Main```.

----

####Alternatively, you can have an executable jar file by using a diffrent build script.

running ```gradle build``` will, by default, use ```build.gradle``` file, which will require passing class path.
Instead, use the second file to get executable jar files

Use 
```gradle build --build-file build-auto-jar.gradle```
or,
```gradle build -b build-auto-jar.gradle```


to run, use
```java -jar build/libs/gradle-custom-build-0.0.2_exec_jar.jar```

----

####Alternatively, you can have a run task [optionally with excutable jar file] by using another diffrent build script.

Use
```gradle build --build-file build-runnable-jar-with-run-task.gradle```
or,
```gradle build -b build-runnable-jar-with-run-task.gradle```
to generate the jar file

Use 
```gradle run --build-file build-runnable-jar-with-run-task.gradle```
or,
```gradle run -b build-runnable-jar-with-run-task.gradle```
to run it without creating jar file

These two can also be chained as:
```gradle build run --build-file build-runnable-jar-with-run-task.gradle```
to build and run in single command