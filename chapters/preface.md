# Preface

This is an example of "frontmatter", which comes before the main text of the book.

## Course Outline

Chapter 01: Codifying Devops

  * Why Devops  
  * History    
  * Principles and Practices  

Chapter 02: Use Case Workshop

  * Description of Use Case
  * Organization Goals
  * Pain Points
  * Diagnosing the issues
  * Solution Design


Chapter 03: Git quick dive

   * Git and Distributed Revision Control
   * Repos
   * Branching and Merging
   * Github
   * Branching Strategy
   * Git References
   * Lab
      * Setting up repos
      * Create a devops repo  

Chapter 04: Ansible quick dive

  * Why Ansible
  * IaaC
  * Convergence
  * Idempotence
  * Ansible Concepts
    * Inventory
    * Playbooks
    * Roles
    * Modules
    * Vars/Templates


Chapter 05: Creating Ansible code for Demo App

  * Playbooks for
    * System Configurations
    * Application Configurations
    * Deployment
  * Additional Code for Provisioning Automation

Chapter 06: Provisioning Automation

  * Vagrant
  * Labs:
    - Create dev env
    - Integrate with Ansible


Chapter 07: Continous Integration

  * Theory

Chapter 08: Setting up a CI Pipeline with Jenkins

  * Setup Jenkins
  * Commit Stage Jobs
    * build/compile
    * unit test
    * static code analysis
  * Artifacts Management
  * Functional Acceptance Testing
  * Deploy to Staging
  * NFR Testing


Chapter 09: Cloud and AWS* Cloud and Devop

  * AWS

Chapter 10: Deploy a prod Environment on AWS

  * Design considerations
    * Availability
    * Scalability
    * Manageability
    * Security  
  * Deploy to prod, integrate with Jenkins


Chapter 11: Containers and Docker

  * Advantages of using containers
    * Portability
    * Consistency
    * Density
    * Eco System
    * Speed
  * Docker quick dive
    * Running Containers
    * Operating Containers
    * Port Mapping
    * Building Docker Images

Chapter 12:  Dockerizing App Stack

  * Build Dockerfiles
  * Create Docker Compose specs

Chapter 13: Kubernetes: Taking Containers to Production

  * COEs and intro to k8s
  * k8s Quick Dive
    * Pods
    * deployments
    * services
    * Ingress
    * rollouts


Chapter 14: Deploying Demo app in Production

  * Deploy k8s Cluster /Minikube
  * Create k8s objects
    * deployment
    * service
    * ingress
  * Release Management
    * Zero Downtime
    * Blue Green
    * Canary

Chapter  15: Monitoring

  * Why Monitoring ?
  * What to monitor
    * Logs
    * APM
    * Health
  * Labs:
    * Setup log monitoring
    * Setup performance monitoring
    * Health Monitoring and Alerting
