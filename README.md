## sdc-calling-custom-java-from-jython

### Overview

This project provides an example of creating and packaging a custom Java class within a jar file, loading the jar file into an [SDC](https://streamsets.com/products/dataops-platform/data-collector/) [Jython Evaluator](https://streamsets.com/documentation/datacollector/latest/help/datacollector/UserGuide/Processors/Jython.html#concept_a1h_lkf_lr), and calling both static and instance methods on the class from the Jython script.


### Requirements
- [Maven](https://maven.apache.org/) is needed to compile the Java class and to package it in a Jar file

- SDC with the Jython stage library 

### Inspect the Java source file

The Java source file is a trivial class with one instance method and one static method:

````
package com.onefoursix;

public class Doubler {

  public long double_it_instance_method(int x){
   return 2 * x;
  }
  
  public static long double_it_static_method(int x){
    return 2 * x;
  }
}
````

### Build the Java project

- Clone this project to your local machine.

- Switch to the ````java```` directory and execute the command

        $ ./build.sh
        
  That will generate the file ````doubler.jar````
  
  
### Import the example pipeline

Import the project's pipeline ````CallingJavaFromJython.json```` into SDC

### Import the jar file into the Jython stage

Import the ````doubler.jar```` file into the Jython stage:

<img src="images/import-jar.png" width="70%">