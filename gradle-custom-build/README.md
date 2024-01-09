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

~~It can be built by running ```gradle build``` command.~~

~~It can be run using ```java -cp build/libs/gradle-custom-build-0.0.1_inital_phase.jar trying.apackage.basic.Main```.~~

##### Update: Modify or delete settings.gradle file to run this.

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

----

### Update: settings.gradle file added
As using specified build script using ```-b``` or, ```--build-file``` is considered deprecated, the new convention is to use ```settings.gradle```, which has an attribute named ```rootProject.buildFileName```, which has to be set to the build script existing in the root of the project folder.

Currently, It is set to
```rootProject.buildFileName = 'build-auto-build-run.gradle'```

which can be updated to set to any above mentioned build scripts, starting with ```build-``` and ending with ```.gradle```.

To build, simply use ```gradle build```
To run, simply use ```gradle run```
To list see the warnings, use ``` --warning-mode all```

All three can be combined as ```gradle build run --warning-mode all```