# Building Docker Images

In this lab, you are going to learn how to bulild images, publish those and work with the docker registry. 

## Building an image manually with docker commit

Lets take the following application as an example. You first need to start by cloning the code,

```
git clone https://github.com/schoolofdevops/facebooc.git

```

after cloning this repo we are going to launch ubuntu image this application running on port 1600 that why we are already exposing port.

```
docker container run -idt --name fb -p 16000:16000 ubuntu bash
```
connect to that container using following command

```
docker exec -it fb bash
```
after connecting that container use following instructions.

Install following package:

* build-essential
* make
* libsqlite3-dev
* sqlite3

```
sudo apt-get update
sudo apt-get install -yq build-essential make libsqlite3-dev sqlite3

```

after installing this packages we need source code cpoy your source code in insisde the container.

```
docker cp facebooc/ fb:/opt/
```
 after copying the data go inside the container

```
docker exec -it fb bash
```

switch the dir.

```
cd /opt/facebooc/
```

then Build the application using following command

```
make all
```  

Run the application using binary

```
bin/facebooc
```

now go to the web browser **host_ip:16000** or **localhost:16000**

then exit the container commit container using following command including your own tag with your docker hub id

```
docker container commit fb initcron/fb:v1
```
After creating image push to docker hub registry

```
docker login
```

```
docker image push initcron/fb:v1
```

### Automatiing image builds with a Dockerfile

Above section we build the image using manual approch. In this we going to dockerfile to build image automation. just clone the repo. using following command.

```
git clone https://github.com/schoolofdevops/facebooc.git

cd facebooc

git checkout docker

```

you can see the Dockerfile

```
cat Dockerfile
```
[output]

```
FROM  ubuntu


WORKDIR /opt/facebooc

RUN  apt-get update &&  \
     apt-get install -yq build-essential make git libsqlite3-dev sqlite3


COPY . /opt/facebooc

RUN  make all

EXPOSE 16000

CMD "bin/facebooc"

```
then build  docker image image

```
docker image build -t initcron/fb:v2 .

```
after build image launch it

```
docker container run -idt -P initcron/fb:v2
```
