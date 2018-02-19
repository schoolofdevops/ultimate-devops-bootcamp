# Jenkins Tools configurations

Once you installed all plugins, we can go ahead to make required changes in configurations.

![Configure Global Security](images/configurations/jenkins_config.png)

![Configure Global Security](images/configurations/config_tools.png)


## Configuring Maven
* Go to section Maven
* Provide name for maven installation
* Select check box to install it automatically and select version to be installed.
![Configure Global Security](images/configurations/maven_config.png)


## Configuring NodeJS
* Go to section NodeJS
* Provide name for nodejs installation
* Select check box to install it automatically and select version to be installed.
* You can provide names to install global modules, which very common for all services.
![Configure Global Security](images/configurations/nodejs_config.png)

## Configuring Go
* Go to section Go
* Provide name for go installation
* Select check box to install it automatically and select version to be installed.
![Configure Global Security](images/configurations/go_config.png)

## Configuring SSH for remote host
* Go to section SSH remote hosts in **Configure Systems** setting.
* Provide host name for hosts to ssh.
* Select ssh port 22.
* We need to provide credentials for same. We can create credentials in **Configure Credentials** menu.
* Select check box to install it automatically and select version to be installed.
![Configure Global Security](images/configurations/ssh_config.png)

## Configuring Artifactory
* Provide the server id for Artifactory server.
* Provide URL of Artifactory server.
* Provide default credentials for Artifactory.
* once you added credentials check the connectivity, it will provide Artifactory version *(e.g 5.8.4)*
![Configure Global Security](images/configurations/artifactory_config.png)

-----
