Maven Cheat Sheet
=================
Some useful commands and snippets for [Apache Maven](https://maven.apache.org/)

Install Maven - Debian Based Systems
------------------------------------
    sudo apt install maven
See: [Installing Apache Maven](https://maven.apache.org/install.html)

Getting started
---------------
See: [Maven Getting Started Guide](https://maven.apache.org/guides/getting-started/index.html)

## Create First Maven Project
    mvn archetype:generate -DgroupId=com.company -DartifactId=app-name -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4
    
POM - Project Object Model
--------------------------
See: [http://maven.apache.org/pom.html](http://maven.apache.org/pom.html)

## Basic POM
```xml
<project 
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.company</groupId>
    <artifactId>app-name</artifactId>
    <version>1.0.0</version>
...
```

```xml
...
    <dependencies>
        <dependency>
            <groupId>...</groupId>
            <artifactId>...</artifactId>
            <version>...</version>
            <scope>compile|runtime|test</scope>
        </dependency>
    </dependencies>
...
```
```xml
...
    <build>
        <pluginManagement>
            <plugins>
                <plugin>
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-compiler-plugin</artifactId>
                    <version>3.8.1</version>
                </plugin>
                ...
                <plugin>
                    ...
                </plugin> 
            </plugins>
        </pluginManagement>
    </build>
</project>
```
See: [Introduction to the POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)

Standard Directory Layout
-------------------------
```code
app-name
|-- pom.xml
`-- src
    |-- main
    |   `-- java
    |       `-- com
    |           `-- company
    |               `-- App.java
    `-- test
        `-- java
            `-- com
                `-- company
                    `-- AppTest.java
```
See: [Standard Directory Layout](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)

Maven Workflow
--------------
| Command | Description |
| --- | --- |
| mvn compile | Compile application sources | 
| mvn test-compile | Compile test sources |
| mvn test | Compile test sources and run unit tests |
| mvn package | Generate a JAR | N/A |
| mvn install | Install JAR in local repository |
| mvn site | Generate website | N/A |
| mvn clean | Remove target dir with build data |

Some Useful commands
--------------------
##### Enabling Maven debug level logs
    mvn clean install –X
##### Viewing the effective POM file
    mvn help:effective-pom
##### Building a dependency tree
    mvn dependency:tree
##### Viewing the dependency classpath
    mvn dependency:build-classpath

Resources
---------
* [Book: Maven Essentials](https://www.amazon.com/Maven-Essentials-Prabath-Siriwardena/dp/178398676X)
* [Book: Apache Maven Cookbook](https://www.amazon.com/Apache-Maven-Cookbook-Raghuram-Bharathan/dp/1785286129)
