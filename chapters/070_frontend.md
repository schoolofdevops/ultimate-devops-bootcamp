# Build pipeline for Front End
Front End pipeline contains two jobs.

* Unit Testing
* Packaging


![Build_Pipeline](images/frontend/Build_Pipeline.png)

## Job 1 (Unit Testing)

The purpose is to validate that each unit of the software performs as designed. unit testing successfully completed, Then the next step is packaging. Suppose unit testing failed, he doesn't perform packaging.

![Unit_Test](images/frontend/unit_test.png)

#### Source Code Management
The Source Code is available at the github.com.
You need to clone it by following url

    https://github.com/microservices-demo/front-end.git

In Build Trigger we have select GitHub hook trigger for GITScm polling.

Whatever is pushed to master i.e. github.com will immediately known by the  **Jenkins server**.

![Source_Code_Management](images/frontend/sourcecode.png)

![Build_Trigger](images/frontend/Build_Trigger.png)

#### Build Environment
To Build the environment we required **NodeJS**

![Build Environment](images/frontend/Build_Environment.png)

#### Build
To Build the Environment we need to install the **npm** you can install it by following Command.   

![Build Environment](images/frontend/Build.png)

## Job 2 (Packaging)
After the successful completion of validation then we go for packaging. After packaging we deploy the package to Artifactory.

![Packaging](images/frontend/Package.png)

### Source Code Management

The Source Code is available at the github.com.
You need to clone it by following url

    https://github.com/udbc/front-end.git/

Once the unit test successfully completed then packages are Triggered.

![Source_Code_Management](images/frontend/sourcecode_package.png)

![Build_Trigger](images/frontend/Build_Trigger_package.png)

### Build Environment
Before starting to build the environment we Delete workspace.

![Build_Environment](images/frontend/Build_Environment_package.png)

### Artifactory Configuration
Once the Unit test and Package are completed the we deploy these artifacts to Artifactory.

![Artifactory_Configuration](images/frontend/Artifactory_Configuration.png)

To download the Artifactory use the following url

    http://188.166.236.188.9081/artifactory

![Artifactory_Download](images/frontend/Artifactory_Download.png)

#### Build
To Build the Environment we need to install the **npm** you can install it by following Command.   

![Build Environment](images/frontend/Build_package.png)

### Artifactory

Once everything is done then the packages are deploy to Artifactory.
![artifactory](images/frontend/artifactory.png)
