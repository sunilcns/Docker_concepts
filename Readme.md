Introduction to Docker
======================

This repository contains notes and basic understanding of **Docker and containerization concepts**, based on learning from GeeksforGeeks.

What is Docker?
------------------

Docker is an **open-source containerization platform** that allows developers to package applications along with their dependencies into lightweight, portable units called containers.
*   Uses **OS-level virtualization** 
*   Containers share the **host OS kernel**
*   Lightweight and fast compared to virtual machines
*   Ensures applications run consistently across environments
    

Problem Before Docker
-----------------------

Before Docker, applications often failed when moved between environments due to:

*   Dependency mismatches  
*   OS differences
*   Configuration issues
    
Common issue:
Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML` 
"It works on my machine"   `

How Docker Solves This
------------------------
Docker packages:
*   Application code
*   Dependencies
*   Runtime
*   Configurations
    

 Result:
*   Same behavior in **dev, test, and production** environments
    

 Key Benefits of Docker
------------------------

*   **Portability** – Run anywhere (local, cloud, servers)
*   **Consistency** – Same environment everywhere
*   **Lightweight** – No full OS required    
*   **Scalability** – Ideal for microservices
*   **Fast startup** – Containers start in seconds
    

Core Components of Docker
----------------------------

### 1\. Docker Engine
*   Core runtime of Docker
*   Uses client-server architecture
*   Manages containers, images, networks
    

### 2\. Docker Image

*   Read-only template
*   Contains application + dependencies
*   Acts as a **blueprint**
    

### 3\. Docker Container

*   Running instance of an image
*   Isolated environment
*   Lightweight and fast
    

Relationship:
Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML` 
Docker Image → Docker Container(blueprint)     (running instance)   `

### 4\. Dockerfile
*   Text file with instructions to build an image
*   Executed step-by-step
    

### 5\. Docker Hub
*   Cloud-based repository for images
*   Used to push/pull images
    

### 6\. Docker Registry
*   Storage system for Docker images
*   Can be public or private
    

Docker Architecture
-----------------------
Docker follows a **client-server model**:

*   **Docker Client** → sends commands
    
*   **Docker Daemon (dockerd)** → executes commands
    
*   **REST API** → communication layer
    

Flow:
Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML` 
User → Docker CLI → Docker Daemon → Containers   `

Common Docker Commands
-------------------------

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`  
docker run      # Run a containerdocker build    # Build an imagedocker pull     # Download imagedocker ps       # List running containersdocker stop     # Stop containerdocker start    # Start container   `

Image vs Container
---------------------

FeatureImageContainerTypeStaticRunningNatureRead-onlyExecutablePurposeBlueprintApplication runtime

Key Takeaways
----------------

*   Docker enables **containerization**, not full virtualization    
*   Containers are **lightweight and portable**
*   Helps solve environment inconsistency issues
*   Core workflow:
    

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   
Dockerfile → Image → Container   `

Use Cases
------------

*   Application deployment
*   Microservices architecture
*   CI/CD pipelines
*   Cloud-native applications

  Write a docker files and submit to docker engine ( platform ). this will convert into image . again using commands image can be converted to a container. 
Lifecycle of Docker -> 
1. Write a docker file. 
2. Execute the file to create image. 
3. Execute the image to create a container 
    
Conclusion
-------------

Docker has become a fundamental tool in modern DevOps by simplifying application deployment, improving consistency, and enabling scalable architectures.
