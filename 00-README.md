# Docker Introduction

Docker is a complex and highly configurable tool. This guide is intended to give you a basic understanding of the common parts of Docker. Once you have completed this guide, the next step is to read the [official docker documentation](https://docs.docker.com/) to start practicing building and customizing your own containers.

## What is Docker?

Docker is a tool that allows you to run applications in a container. It is similar to a virtual machine, but it is much smaller and faster. Containers are also more secure than virtual machines because they do not share resources with other containers. They are also easier to manage because they do not require any special software to install or configure.

## In the Beginning, There Were Virtual Machines

Before we dive into containers, it's will be helpful to take a moment to understand the origin story of the prehistoric virtual machine.

A virtual machine is a digital representation of a physical machine. This is commonly the computer hardware and any operating systems and/or additional installed software. Virtual machines are often used to run multiple operating systems simultaneously on a single computer. Virtual machines are also used to run applications that require a specific operating system or hardware configuration.

A virtual machine is constructed as a computer file, typically called an image. The file represents the hardware, software, and data that make up the virtual machine.

Special virtualization software is required to interpret and execute the virtual machine image. This software is called a hypervisor. The hypervisor is responsible for creating and managing the virtual machine and the hosts resources.

The hardware required for a virtual machine is called the host. The host is the physical computer that runs the hypervisor. The host provides the resources required to run all of the virtual machines.

## When containers came along

As you might imagine, virtual machines are not very efficient. They require a lot of resources to run. They also require a lot of time to start up and shut down. This is because they have to emulate the hardware of the host machine. This is often a slow process. They also consume a large amount of disk space because they have to store all of the data required to run the virtual machine including the entire operating system and any additional software.

Do most software developers need a full virtual machine to run their applications? Probably not. Most developers only need a small portion of the host machine to run their applications. This is where containers come in.

Containers came along as a virtual machine tool that focuses more on the software application than the hardware. Containers are a new way to package and run applications. They are similar to virtual machines, but they are much smaller and faster. Containers are also more secure than virtual machines because they do not share resources with other containers. They are also easier to manage because they do not require any special software to install or configure.

Containers often run a slimmed down Operating System. Linux is the most popular operating system for containers. This is because Linux is open source and can be built to have small footprint. It is also very stable and secure.

There are a variety of containerization tools available. Probably the most popular is Docker. Docker is an open source project that provides a platform for developers to build, ship, and run applications in containers.

Docker is platform independent. It can run on Linux, Windows, and Mac OS X. It can also run on a variety of cloud platforms including Amazon Web Services, Google Cloud Platform, and Microsoft Azure.

Docker is also very easy to use. It provides a simple command line interface that allows you to create, start, stop, and delete containers. It also offers a graphical interface (Docker Desktop) that allows you to manage your containers

## Containers are disposable

Containers are designed to be ephemeral, lightweight, and portable. They can easily be created, started, stopped, and deleted. When a container is stopped, all of its data is lost. This is because containers are designed to be stateless. They do not save any data on the host machine. They only save data in memory while they are running. When a container is stopped, all of its data is lost.

>Let's imagine we have a milk container that need to be disposed. With docker we can tell it to take care of disposing the old milk and rinsing the container.

## Virtual Network (Networks)

What use is a computer that can't communicate with other computers?
The Docker network is a virtual network that allows containers to communicate with each other and with the world wide web. It is similar to a physical network in that it has a network interface card (NIC) and an IP address. It is also similar to a physical network in that it has a subnet mask and a default gateway.

## Virtual Storage (Volumes)

Docker's approach to data storage is akin to a USB drive that can be plugged in and out of containers. Or rather a network attached storage that can be mounted into multiple containers.

Docker calls this a volume. A volume is a directory on the host machine that is mounted into a container. The location on the host machine can be configured when the container is created, or left in a default location specified by the dockers default volume path. The location of the mounting path inside of the container is also configurable.

### Other features of volumes include

- it can be formatted with any file system you want.
- it can be mounted into a container.
- it can be write protected.
- it can be shared between containers at the same time.

## Dockerfile

A Dockerfile is a text file that contains instructions for building a Docker image. This is where you define the software configuration of your container.

>Dockerfile is your shopping list of what you need to buy to refill the container.

## Image

A docker image is a snapshot of everything you need for filling your container. It can contain the details about the operating system, the software, and the data and configuration files.

A Docker image is read-only. It cannot be modified. It can only be created and deleted.

Images are not running. They are a frozen state. They cannot be interacted through a shell. They can only be interacted with through the Dockerfile during the build process. Images must be started in a container before they can be interacted with.

Containers are the virtual machine
Images are the configuration and state of the virtual machine when started

Stopping a container will delete any changes made to the container and anything that is not saved in the image.

## Putting the parts together

Now that we have a basic understanding of the parts of Docker, putting them together to create your custom virtual machine is a three step process. 

### Step 1: Create a Dockerfile

The first step is to create a `Dockerfile`. This is a text file that contains instructions for building a Docker image. It contains a list of commands that can be executed to build the image. See the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/) for more information about the commands that can be used in a Dockerfile.

### Step 2: Build the image

The next step is to build the image. This is done by running the `docker build` command. This command will read the Dockerfile and execute the commands in it. It will then create an image based on the commands in the Dockerfile.

### Step 3: Run the image in a container

The final step is to run the container. This is done by running the `docker run` command. This command will start the container and run the commands in it. It will then print out the output of the commands.

Once your container is running, you can interact with it using the `docker exec` command. This command allows you to run commands inside the container. You can also use the `docker attach` command to attach to the container and interact with it using a shell.

When you're done, you can shut down the container using the `docker stop` command. This will stop the container and delete it. You can also use the `docker rm` command to delete the container.

## Remembering the commands

One easy way to get a quick printout of the main commands is to run the `docker` command with no arguments. This will print out a list of the most common commands along with a brief description of what they do.

## Prebuilt images (Docker Hub)

Remember when I said creating a container is a three step process? Well, what if I told you that you can do it in one step? That's right! You can create a container in one step using the `docker run` command along with a prebuilt container from a public container registry like docker hub.

Let's make a container that runs a simple web server.

In a terminal, run the following command:

```bash
docker run -p 8080:80 nginx
```

Here, we use the `docker run` command to create the container and run it. The `-p` flag to specifies the port that the web server should listen on. This will allow us to access the web server from our host machine via port 8080. Finally, we use the prebuilt `nginx` image from docker hub that has a starter nginx server ready to go.

## Configuring the container

Remember that containers are disposable. So how do we save our configuration changes?

The most common way is to stop the container, change the `Dockerfile`, rebuild the image, and rerun it in a new container.

Another way is use the `docker commit` command to save our changes to a new image. This will create a new image based on the changes we made to the container.


>This is a high-level overview. For more information, see the [official docker documentation site here.](https://docs.docker.com/)