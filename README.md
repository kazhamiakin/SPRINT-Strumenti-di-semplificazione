TAE and WAE API projects
===========

Description
===========

The project exposes the Text Adaptation Engine API and the Workflow Adaptation Engine Model Repository

Requirements
===========

The following should be installed in order to execute the engines:

    1. Java 8
    2. MongoDB 
    
Installation
===========

The engine runtime is implemented as a Spring Boot standalone application and can be built with Apache Maven.
To accomplish this, execute (within the project directory)

<code>
./mvnw package
</code>      
       
This produces the executable jar in `target` folder. To execute the engine use the following command:

<code>
java -jar target/simpatico-adaptation-engines-0.0.1-SNAPSHOT.jar
</code>       
       
Configuration
===========

The engine configuration relies on a series of configuration properties deriving from Spring Boot properties and
the specific engine properties. It is possible to pass the properties either as execution parameters (`-D<propertyname>=<propertyvalue>`) or defining them in the `src/main/resources/application.properties`. 
The following properties are relevant:

  - `server.port`: Defines the HTTP port where the engines will listen   
  - `server.contextPath`: the engine context path used for the exposed endpoint (simp-engines)
  - `db.name`: name of the Mongo database
  - `tae.mode.proxy.enabled`: defines whether the instance works as a proxy to a remote Text Adaptation Engine API
  or implements the functionality internally. The TAE functionality is resource consuming; if the engine works 
  in test mode or does not require instantiating this functionality set this value to true.
  - `tae.mode.proxy.endpoint`: Endpoint of the remote TAE instance. Required in case of proxy mode is enabled.
  
Documentation
============

The API exposes the Swagger documentation at the following endpoints
  - `<context-path>/apidocs`: The raw swagger 2 API definition
  - `<context-path>/swagger-ui.html`: The Swagger UI interface of the component
  
             
    