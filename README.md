Maven Cheat Sheet
=================

Some useful commands and snippets for [Apache Maven](https://maven.apache.org/)

POM - Project Object Model
--------------------------
See [http://maven.apache.org/pom.html](http://maven.apache.org/pom.html)

## Basic POM

```xml
<project 
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.company</groupId>
  <artifactId>project-name</artifactId>
  <version>1.0.0</version>
</project>
```

Some Useful commands
--------------------

#### Enabling Maven debug level logs
```console
$ mvn clean install –X
```
#### Viewing the effective POM file
```console
$ mvn help:effective-pom
```
#### Building a dependency tree
```console

$ mvn dependency:tree
```
#### Viewing the dependency classpath
```console
$ mvn dependency:build-classpath
```


