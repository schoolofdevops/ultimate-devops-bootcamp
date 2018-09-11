# Capstone Project
## Robotshop
Robot Shop is a sample microservice application you can use as a sandbox to test and learn containerised application orchestration and monitoring techniques. It is not intended to be a comprehensive reference example of how to write a microservices application, although you will better understand some of those concepts by playing with Robot Shop. 
### Microservices
Robot Shop is composed of following microservices.
```
Robot Shop
  \
  |--- Web (HTML)
  |--- Cart (Node)
  |--- Catalogue (Node)
  |--- Dispatch (Go)
  |--- User (Node)
  |--- Shipping (Java)
  |--- Payment (Python)
  |--- MySQL
  |--- Redis
  |--- RabbitMQ
  |--- MongoDB
```

### Goal:  
  Build and Deploy all the microservices in Robot Shop using tools such as Git, Jenkins, Docker, Kubernetes, Prometheus, CSPs(AWS and GCP).

#### Step 1:  
 Create and commit(in future) all the code to a `Git` repostory hosted on Github.  
   * **Tools involved**:  
      * Git  
      
#### Step 2:  
 Create one VM with following properties.  
  * **VM Properties**:  
       * Cloud: `AWS`  
       * OS: `Ubunt 16.04`  
       * Size: `t2.micro`  
       * Name: `build-server`  
       * Open Ports: `8080`, `22`  
  * **Tools involved**:  
       * AWS console  
       
#### Step 3:  
  Install *Jenkins(latest)* and *Docker(latest)* on the VM using `Ansible(version 2.5)`.  
  *  **Tools involved**:  
        * Ansible  
        
#### Step 4:  
  Create a `Jenkins Pipeline` which *builds* and *tests(unit test)* *Shipping* service.  
  *  **Tools involved**:  
        * Jenkins  
        
#### Step 5:  
  Create `Dockerfiles` for all the following services.  
  * **Services**:
    * Web  
    * Cart  
    * Catalogue  
    * Dispatch  
    * User  
    * Shipping  

    
  *  **Tools involved**:  
        * Docker  
        
#### Step 5:  
  Create Jenkins jobs which create and pushe `Docker images` for the following services.  
  * **Services**:
      * Web  
      * Cart  
      * Catalogue  
      * Dispatch  
      * User  
      * Shipping  
      
      
  * **Tools involved**:  
      * Jenkins  
      * Docker  
      
#### Step 6:  
  Create a `Docker-compose` file for the Robot Shop application with following properties.  
  *  **Services**:
      * Web  
      ```
       port: 8080  
       depends_on:  
        - catalogue  
        - user  
        - shipping  
        - payment 
      ```  
      * Cart  
      ```
        depends_on:  
         - redis 
      ```  
      * Catalogue  
      ```
        depends_on:  
         - mongodb  
      ```  
      * Dispatch  
      ```
        depends_on:  
         - rabbitmq  
      ```  
      * User  
      ```
        depends_on:  
         - mongodb  
         - redis  
      ```  
      * Shipping  
      ```
        depends_on:  
         - mysql  
      ```  
      * MySQL  
      ```
        cap_add:  
         - NET_ADMIN  
      ```  
      * RabbitMQ  
      * Redis  
      * MongoDB  

      
*  **Tools involved**:  
  * Docker  
        
#### Step 7:  
Create a `GKE` Clsuter, Create K8s manifests for the entire stack and deploy them.  
*  **Tools involved**:  
  * GCP  
  * GKE
  * Kubernetes
