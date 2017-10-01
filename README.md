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
/path/to/repo$ ./gradlew build jar
```

### Windows

Navigate to your local clone of this git repository, and run:
```
/path/to/repo$ gradlew.bat build jar
```

Note that this performs the `build` task, followed by the `jar` command,
it doesn't simply tell gradle to build the JAR.

### Running WordCount

If you have a terminal open on a machine with a hadoop installation, e.g. AWS
EMR, Google DataProc, local installation, etc... and you already have the 
JAR available as `superCoolJarName.jar`, as well as have the [included 
script](./get-data.sh) locally just execute:
```bash
$ ./get-data.sh #wait for data to download
$ hadoop fs -mkdir -p words #dataproc doesn't automatically create /home/user/ in HDFS
$ hadoop fs -put *.txt words
$ hadoop jar superCoolJarName.jar words wordsOutput
```

to get the data and run the jar.  You can get some local results by doing:
```bash
$ hadoop fs -get wordsOutput
$ head -n20 wordsOutput/part-r-00000
```
