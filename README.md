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
```code
mvn archetype:generate -B
                    -DarchetypeGroupId=org.apache.maven.archetypes
                    -DarchetypeArtifactId=maven-archetype-quickstart
                    -DarchetypeVersion=1.4
                    -DgroupId=com.company
                    -DartifactId=app-name
                    -Dversion=1.0.0
```
    
    
POM - Project Object Model
--------------------------
The basic POM is inherited from the super POM which is the system wide POM for any Maven project unless a parent POM is supplied. Default repository: [Maven Central](http://repo.maven.apache.org/maven2)  
See: [Introduction to the POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)

## Basic POM
```xml
<project 
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.company</groupId>
    <artifactId>app-name</artifactId>
    <version>1.0.0</version>
    ...
```
##### Dependencies
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
##### Plugins
```xml
    ...
    <build>
        ...
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
        ...
```
##### Directories
```xml
        ...
        <directory>${project.basedir}/target</directory>
        <outputDirectory>${project.build.directory}/classes</outputDirectory>
        <finalName>${project.artifactId}-${project.version}</finalName>
        <testOutputDirectory>${project.build.directory}/test-classes</testOutputDirectory>
        <sourceDirectory>${project.basedir}/src/main/java</sourceDirectory>
        <scriptSourceDirectory>${project.basedir}/src/main/scripts</scriptSourceDirectory>
        <testSourceDirectory>${project.basedir}/src/test/java</testSourceDirectory>
        ...
```
##### Resources
```xml
        ...
        <resources>
            <resource>
                <directory>${project.basedir}/src/main/resources</directory>
            </resource>
        </resources>
        <testResources>
            <testResource>
                <directory>${project.basedir}/src/test/resources</directory>
            </testResource>
        </testResources>
        ...
    </build>
    ...
</project>
```
See: [Project Object Model](http://maven.apache.org/pom.html)

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
##### Find inconsistent dependencies
    mvn dependency:analyze

Resources
---------
* [Book: Maven Essentials](https://www.amazon.com/Maven-Essentials-Prabath-Siriwardena/dp/178398676X)
* [Book: Apache Maven Cookbook](https://www.amazon.com/Apache-Maven-Cookbook-Raghuram-Bharathan/dp/1785286129)
