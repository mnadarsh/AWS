# Other Compute Section

  **What is Docker?**
  
    • Docker is a software development platform to deploy apps.
    • Apps are packaged in containers that can be run on any OS.
    • Apps run the same, regardless of where they’re run.
      • Any machine
      • No compatibility issues
      • Predictable behavior
      • Less work
      • Easier to maintain and deploy
      • Works with any language, any OS, any technology
    • Scale containers up and down very quickly (seconds).
  
  **Where Docker images are stored?**
  
    • Docker images are stored in Docker Repositories
    • Public: Docker Hub https://hub.docker.com/
    • Find base images for many technologies or OS:
      • Ubuntu
      • MySQL
      • NodeJS, Java…
    • Private: Amazon ECR (Elastic Container Registry).
  
  ![Docker](https://github.com/mnadarsh/AWS/blob/master/Docker.PNG "Docker")
  
  **Docker versus Virtual Machines**
  
    • Docker is ”sort of” a virtualization technology, but not exactly.
    • Resources are shared with the host => many containers on one server.
  
  ![Docekr-vs-VM](https://github.com/mnadarsh/AWS/blob/master/Images/Docekr-vs-VM.PNG "Docekr-vs-VM")
    
 **ECS**
 
     • ECS = Elastic Container Service.
     • Launch Docker containers on AWS.
     • You must provision & maintain the infrastructure (the EC2 instances)
     • AWS takes care of starting / stopping containers.
     • Has integrations with the Application Load Balancer.
  
 ![ECS](https://github.com/mnadarsh/AWS/blob/master/Images/Images/ECS.PNG "ECS")
 
 **Fargate**
 
    • Launch Docker containers on AWS
    • You do not provision the infrastructure (no EC2 instances to manage) – simpler!
    • Serverless offering.
    • AWS just runs containers for you based on the CPU / RAM you need.
  
  ![Fargate](https://github.com/mnadarsh/AWS/blob/master/Images/Fargate.PNG "Fargate")
  
 **ECR**
 
    • Elastic Container Registry.
    • Private Docker Registry on AWS.
    • This is where you store your Docker images so they can be run by ECS or Fargate.
  
 ![ECR](https://github.com/mnadarsh/AWS/blob/master/Images/ECR.PNG "ECR") 
  
