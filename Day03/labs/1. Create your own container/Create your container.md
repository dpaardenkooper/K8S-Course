# Creating a simple container app

The purpose of this lab is to create your own container.
As an example, nginx is used with a custom homepage.

## Required for this course

An Environment where you can run docker.
Visual Codes must be available.

## Create a Dockerfile
Make a directory. For example "docker-manifest.
Open the new directory

```bash
mkdir docker-manifest
cd docker-manifest
```

Make a file called "Dockerfile"

```bash
mkdir docker-manifest
cd docker-manifest
```

Open de Dockerfile in your visual Codes and add the following content:

```bash
FROM nginx
COPY index.html /usr/share/nginx/html
```

Save the file.

> **Remark**
> Of course you can add more lines of code. But for now, let's just keep it simple.


## Create homepage 
Next, create your own home page config.
Make in the same directory, a new file called "index.html".

```bash
vim index.html
```

Add some content. 

```bash
<!DOCTYPE html>
<html>
   <body style="background-color:rgb(127, 178, 210);">
      <h1>Hello World Demostratie - Webapplicatie - Build this year in 2024</h1>
      <h2>Van harte welkom!</h2>
      <p>Application Version: V1</p>
   </body>
</html>
```

Save the file.

```bash
wq!
```

## build your container.
In the next step you will build your container.
Open a terminal. Go to the location where the files are.

```bash
docker build -t itimpressive/myapp:v1 . 
```

The build process starts.


## Check your image is there.
Let's verify if your image is there.

```bash
docker images
```


## Run your container.
Let's run your container.

```bash
docker run --name mydemo -p 80:80 -d itimpressive/myapp:v1
```

## Check if your container runs.
Let's run your container.

```bash
docker ps
```

## Check if your homepage runs.
Let's see if the homepage is reachable (with the remark it only works locally on your machine).
Open your favorite browser and type "localhost".

```bash
localhost
```

![alt text](./homepage.png "Homepage of your container!")


## Remove the container.
Let's stop the container.
Check first it's id and then remove it

```bash
docker ps
docker rm <containerid>
```

## Remove the container image.
Let's stop the container.

```bash
docker images
docker rmi image itimpressive/myappser:v1
docker images
```