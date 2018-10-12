# How to create JAVA jars files.

 Java 8 is a revolutionary release of the world’s #1 development platform. It includes a huge upgrade to the Java programming model and a coordinated evolution of the JVM, Java language, and libraries. Java 8 includes features for productivity, ease of use, improved polyglot programming, security and improved performance. Welcome to the latest iteration of the largest, open, standards-based, community-driven platform.[Official Website Link](http://www.oracle.com/technetwork/java/javase/overview/java8-2100321.html).

### WINDOWS Operating System - Microsoft Windows 10

- JAVA-8 Version: 1.8.0_171

    - Prerequisites: No prerequisites. JAVA should be compatible with the platform.
    
    - Follow the steps given below:
        - Start Command Prompt.
        - Navigate to the folder that holds your class files
        - Set path to include JDK’s bin. 
        - Compile your class(es): **`javac *.java`**
        - Create a manifest file: **`echo Main-Class: <your_class_name> >manifest.txt`**
        - Create the JAR file: **`jar cvfm <your_class_name>.jar manifest.txt *.class`** OR **`jar cvfe <your_class_name>.jar <your_class_name> *.class`**
        - Test your jar: **`Craps.jar`** OR **`java -jar Craps.jar`**
				
    - Note: To avoid any errors, make sure that class path for the main class is set correctly.
      
    - You are ready to use the JAR file on any platform that has JAVA JDK environment on top of it.

