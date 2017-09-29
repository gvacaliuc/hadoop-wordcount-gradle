# MapReduce WordCount

This is an example implementation of a word counting application on Hadoop
MapReduce.  The [WordCount
code](./src/main/java/edu/comp330/lab1/WordCount.java) was appropriated from
[Chris Jermaine's F2017 COMP330
Lab1](http://cmj4.web.rice.edu/HadoopActivity/WordCount.java), taught at Rice
University.

## How to build the JAR

It's not necessary to use an IDE to build this JAR, however you can if you'd
like to.  Refer to your IDE's documentation on importing a project which uses
gradle for building.  For example, Intellij will automatically try to 
import the project as a gradle project when importing this git repo.

### Unix (Linux / MacOS)

Navigate to your local clone of this git repository, and run:
```bash
/path/to/repo$ ./gradlew build shadowJar
```

### Windows

Navigate to your local clone of this git repository, and run:
```
/path/to/repo$ gradlew.bat build shadowJar
```

Note that this performs the `build` task, followed by the `shadowJar` command,
it doesn't simply tell gradle to build the "Shadow JAR".
