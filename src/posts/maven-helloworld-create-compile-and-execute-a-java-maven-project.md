---
layout: layouts/post.njk
title: Maven HelloWorld - Create, Compile and Execute a Java Maven Project
metaTitle: Maven HelloWorld
metaDesc: Create, Compile and Execute a Java Maven Project
date: 2018-09-01T02:49:43.337Z
tags:
  - java
  - maven
  - tutorial
---
### Create
```bash
mvn archetype:generate
```
This will start an interactive process for generating the new project. There will be prompts for the groupId, artifactId, and version (among other things).

To skip the interactive method, use the following syntax instead:
```bash
mvn archetype:generate -DgroupId=ca.salmanfs.javaPractice -DartifactId=HelloWorld -DinteractiveMode=false
```

### Compile
Maven built us a basic Java file that prints "Hello World!"
We can compile that now:
```bash
mvn compile
```

This will execute the Maven build lifecycle phases of 'validate' and 'compile'.
This is what Maven is doing for us:
```bash
mkdir -p target/classes/
javac -d target/classes/ -cp src/ src/main/java/ca/salmanfs/javaPractice/App.java
```

### Execute
```bash
java -cp target/classes/ ca.salmanfs.javaPractice.App
```
The `-cp` flag tells the Java interpreter where to find the package that we specify.