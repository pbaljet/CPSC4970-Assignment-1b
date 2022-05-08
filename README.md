# CPSC4970-Assignment-1b

This assignment has you setting up and using Apache Maven to build a basic Java Hello World application.  The Java application was created by using the Maven archetype [maven-archetype-quickstart](https://maven.apache.org/archetypes/maven-archetype-quickstart/), which provides a ready to build Java application with a single Java class and associate test.  This is the simplest type of Maven configuration.
```
    mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes \
        -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4
```

Your are welcome to start using an IDE as you edit source code files.  But it is encouraged to still use git and maven at the command line to re-enforce the concepts.  IDE's essentially run these commands for you.

Do the follow:

1. Clone the following repository for the assignment:
    ```
    git clone https://gitlab.com/cpsc4970-sum-a/<your project>/assignment-1.git
    ```
2. Examine the .gitignore file
   - It contains files that should be ignored by git and should be edited for any files any IDE configuration files or directories.  The existing **.idea** directory is for Intellij IDE.
   - The **target** directory is where Maven outputs all of it's working files and build artifacts. 


3. Make sure you are running Java JDK 11
    ```
    java -version
    ```
4. Run Maven compile:
    ```
    mvn compile
    ```
   **target** directory should have been created on successful build.  Examine it's contents.  The compiled classes can be found under the **classes** directory

5. Run Maven test:
    ```
    mvn test
    ```
   Examine **target** directory and examine it's contents.  You will notice additional directories related to running automated tests.

6. Run Maven clean:
    ```
    mvn clean
    ```
   The **target** directory is now removed and all working files are deleted.


7. Package our Java application into a jar file.
   ```
   mvn package
   ```
   The **target** directory will not contain the following file:
   ```
   assign1b-1.0-SNAPSHOT.jar
   ```
   Run the following to examine the contents:
   ```
   tar -tf target/assign1b-1.0-SNAPSHOT.jar
   ```
8. Install the package in your local repository
   ```
   mvn install
   ```
   Examine the **~/.m2/repository/** directory and look for the directoy and files related to the **assign1b-1.0-SNAPSHOT.jar** package.