#### Gradle custom multi project

This gradle java multi-project was not generated using gradle init tool, but was manually created.

This project has three sub-projects, namely:

> sub-project-1

> sub-project-2

> sub-project-3

with dir structure as follows:

>sub-project-n
>> src
>>> main
>>>> java
>>>>> package
>>>>>> Main.java

>> build.gradle

With outer dir as follows:

>.gitignore

>build.gradle

>README\.md

>settings.gradle

----

This gradle project can be built using: ```gradle build```
and, run using: ```gradle run```

----

Additionally, any sub-project can be built using ```gradle :sub-project-n:build```, where ```n``` is the number of sub-project as specified in the sub-project name, no spaces are allowed between.

To run any sub-project, use ```gradle :sub-project-n:run```, where ```n``` is the number of sub-project, similar as previously explained.

Both can be combined as well, using ```gradle :sub-project-n:build :sub-project-n:run```

---
