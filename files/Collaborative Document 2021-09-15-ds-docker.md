![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document 2021-09-15-ds-docker

2021-09-15 Docker Introduction.

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: [link](https://tinyurl.com/mfk4tpjk)

Collaborative Document day 1: [link](https://tinyurl.com/mfk4tpjk)

Collaborative Document day 2: [link](https://tinyurl.com/dzw27zwj)

## 👮Code of Conduct

* Participants are expected to follow those guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, type `/hand` in the chat window.

To get help, type `/help` in the chat window.

You can ask questions in the document or chat window and helpers will try to help you.

## 🖥 Workshop website

[link](https://esciencecenter-digital-skills.github.io/2021-09-15-ds-docker/)

🛠 Setup

[link](https://esciencecenter-digital-skills.github.io/2021-09-15-ds-docker/#setup)

Download files

[link](https://carpentries-incubator.github.io/docker-introduction/files/docker-intro.zip)

## 👩‍🏫👩‍💻🎓 Instructors

Djura Smits, Jens Wehner

## 🧑‍🙋 Helpers

Carlos Martinez Ortiz, Francesco Nattino

## 🗓️ Agenda

| | |
|-|-|
|09:00 | Welcome and Icebreaker|
|09:15| Introducing Docker containers and container images|
|09:45| The Docker command line|
|10:15 | Coffee break |
|10:30| Exploring and Running Containers |
|11:00 | Docker Hub |
|11:15 | Cleaning up Containers |
|11:30 | Tea break|
|11:45 |Creating your own container images|
|12:30 | Wrap-up|
|13:00| END|

## 🔧 Exercises


### Exercise 1: What’s Your Experience?

Take a minute to think about challenges that you have experienced in using scientific software (or software in general!) for your research. Then, share with your neighbors and try to come up with a list of common gripes or challenges.

**Answers**:

Tijmen (KNMI) --> No proper source,  not the latest source, Makefiles which bind global packages / react on global variables /, no proper MakeFile. Dependecies not clear, not supported, runs only Windhoos. Compile-able for old ARM only, Documentation?
Haili: installation problems on Mac (M1), requirements not specified
Leonardo: setting up environments, reproduceability , compatibility with updates (breakage), scalability, lack of documentation
Malbert: Installation, not being supported (anymore), not all files (databases) available, limited documentation
Izzy: runs only on Windows (often wfor sensor-specific programs). no idea how it works, not reproducible.
Richard: versions of software related to source code which need to be related for reproducability of research results. Switching between them is not easy to do.
Xiaoming: needing some specific version of package, but the user usually don't notice it, or there is no information about the package in the documentation.
Parisa: Setting the environment for researchers with limited level of technical skills.\
Shengnan: toolbox upgrading. You would like to enjoy the new functions of new version but have to take care of the legacies. 
Hari: PP 
Jairus: Undocumented dependencies
Michela: reproducibility , technical details missing from method sections of manuscripts, compatibility between platforms 
Eduarda: version sustainability; software can be hard to install, if you are comparing several of them then it's a huge pain; reproducibility
Shashank: Installation takes (inordinate amount of) time as a lot of it is poorly distributed.
Manuel: Difficulty in compiling the source code, many times because of lacking of some dependencies in the target operative system. Also some problems with requiring specific version of compiler.
Marianna: Reproducibility, (long-term) software sustainability 

### Exercise 2: Software and Science

Again, take a minute to think about how the software challenges we’ve discussed could impact (or have impacted!) the quality of your work. What can go wrong if our software doesn’t work?

**Answers**:

Tijmen --> Currently it slows us down a lot: it takes a lot of time just to "keep it up". The bigger problem is the future: we cannot support this for ever, so there is a big risk in the long-term rechears
Richard: Currently I work with one environment with a fixed set of Python packages. So no problems so far.
Izzy: leaves a lot of unanswered questions... what's *actually* going on, under the hood, that I don't know about?
Haili: lost time, errors/differences due to different versions
Leonardo: slows it down, limits options, extra time required in training/maintenance
Eduarda: requires more maintenance thus more time (debugging as well); might not reproduce my work.
Shengnan: 100% Reproducibility is hard to achieve.
Malbert: Takes time to fix, lack of documentation could make interpretation difficult
Michela: "wasting" time when trying to integrate findings from scientific literature that are hard to reproduce, efficiency
Jairus: Slows down the work, the reproducilibity and validity of the resulting data is questionable at times
Shashank: Discourages attempts to reproduce other people's work / workflows.
Xiaoming: the software can't run at all. Or some weird error messages show up which is hard to debug.
Marianna: Problems for re-use, verification and open science principle application

### Check set up

Does `docker --version` work?

**Answers**:

Tijmen --> Yahs!  --> Docker version 20.10.8, build 3967b7d
Richard: Docker version 20.10.8, build 3967b7d
CONTAINER ID   IMAGE                    COMMAND                  CREATED      STATUS         PORTS                                       NAMES
e05726c7ca0b   jupyter/scipy-notebook   "tini -g -- start-no…"   5 days ago   Up 5 minutes   0.0.0.0:8888->8888/tcp, :::8888->8888/tcp   goofy_payne

Izzy: `Docker version 20.10.8, build 3967b7d`
Shengnan: Yes
Xiaoming: Docker version 20.10.8, build 3967b7d
Malbert: Yes
Leonardo: Docker version 19.03.8, build afacb8b7f0
Jairus: Docker version 20.10.8, build 3967b7d, so yes
Haili: Docker version 20.10.5, build 55c4c88
Shashank: yes
Marianna: Docker version 20.10.8, build 3967b7d
Hari: Docker version 20.10.8, build 3967b7d
Michela: Docker version 20.10.8, build 3967b7d
Eduarda: Docker version 20.10.8, build 3967b7d
Parisa: yes

### Exercise 3: Exploring a command
Run `docker --help` and pick a command from the list. Explore the help prompt for that command. Try to guess how a command would work by looking at the Usage: section of the prompt.

**Answers**:

- Eduarda Gervini Centeno; docker version --help
- Haili Hu: docker search --help
- Harikrishnan Vijayakumaran: done 
- Hédia Tnani docker pull --help
- Izzy Hendriks: `docker create --help`
- Jairus Beije: Done, docker pull --help
- Leonardo Honfi Camilo: Done
- Malbert Rogers: done (docker create --help)
- Manuel Cardosa: docker --help logs
- Marianna Avetisyan: `done (docker top --help)`
- michela busana: docker inspect --help done
- Mohamed Taoufik TEKAYA
- Parisa	Zahedi: docker create --help
- Richard van Dijk: > docker start/stop goofy_payne
- Sebastian Costamagna
- Shashank Shekhar	Harivyasi: yes
- Shengnan Liu: Yes 
- Tijmen Molema  --> Done (docker info --help)
- Xiaoming Tiang: docker build --help
- Franciso Regateiro : 


### Exercise 4: Check on Your Images
What command would you use to see if the ``hello-world`` Docker image had downloaded successfully and was on your computer? Give it a try before checking the solution.

**Answers**:

- Eduarda Gervini Centeno: docker image ls
- Haili Hu: docker image ls
- Harikrishnan Vijayakumaran:
- Hédia Tnani:`docker image ls`
- Izzy Hendriks: `docker image ls | grep 'hello-world'`
- Jairus Beije: docker image ls
- Leonardo Honfi Camilo: `docker image list`
- Malbert Rogers: `sudo docker image ls`
- Manuel Cardosa: `docker image ls` or `docker images 'hello-world'`
- Marianna Avetisyan: `docker image ls`
- michela busana: `sudo docker image ls`
- Mohamed Taoufik TEKAYA:
- Parisa Zahedi: docker image ls
- Richard van Dijk: see below
```
PS C:\Users\richa> docker pull hello-world
Using default tag: latest
latest: Pulling from library/hello-world
b8dfde127a29: Pull complete
Digest: sha256:7d91b69e04a9029b99f3585aaaccae2baa80bcf318f4a5d2165a9898cd2dc0a1
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
PS C:\Users\richa> docker image ls
REPOSITORY               TAG       IMAGE ID       CREATED        SIZE
python                   slim      66f4843b721f   7 days ago     122MB
jupyter/scipy-notebook   latest    a5289ef1bc38   8 days ago     2.54GB
hello-world              latest    d1165f221234   6 months ago   13.3kB
docker/whalesay          latest    6b362a9f73eb   6 years ago    247MB
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: done
- Shengnan Liu: docker image inspect hello-world
- Tijmen Molema: sudo docker image ls
```
        REPOSITORY        TAG       IMAGE ID       CREATED        SIZE
        python            slim      66f4843b721f   7 days ago     122MB
        hello-world       latest    d1165f221234   6 months ago   13.3kB
        docker/whalesay   latest    6b362a9f73eb   6 years ago    247MB
```
- Xiaoming Tiang: `docker image ls`
- Franciso Regateiro: docker image ls


### Exercise 5: Run the Alpine Docker container
Try downloading and running the `alpine` Docker container. You can do it in two steps, or one. What are they?

**Answers:**

- Eduarda Gervini Centeno: docker run alpine
- Haili Hu: `docker run alpine`
- Harikrishnan Vijayakumaran:
- Hédia Tnani:`docker run alpine`
- Izzy Hendriks: one step: `docker run alpine`, two step: `docker pull alpine`, `docker run alpine`
- Jairus Beije: (`docker pull alpine` + ) `docker run alpine`
- Leonardo Honfi Camilo: `docker run alpine`
- Malbert Rogers: `sudo docker run alpine`
- Manuel Cardosa: `docker pull alpine` && `docker run alpine`
- Marianna Avetisyan: `docker pull alpine`, `docker run alpine`
- michela busana: `sudo  docker run alpine`
- Mohamed Taoufik TEKAYA:
- Parisa Zahedi:`docker run alpine
- Tijmen Molema: sudo docker pull alpine; sodu docker run alpine;
- Richard van Dijk: see below
```
PS C:\Users\richa> docker run alpine
Unable to find image 'alpine:latest' locally
latest: Pulling from library/alpine
a0d0a0d46f8b: Pull complete
Digest: sha256:e1c082e3d3c45cccac829840a25941e679c25d438cc8412c2fa221cf1a824e6a
Status: Downloaded newer image for alpine:latest
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: done
- Shengnan Liu: 
- Tijmen Molema: 
- Xiaoming Tian: `docker run alpine`
- Franciso Regateiro:docker run alpine

**Solution**:

Two steps
```
$ docker pull alpine
$ docker run alpine
```
One step
```
$ docker run alpine
```

### Exercise 6: Hello World, Part 2

Can you run the `alpine` container and make it print a “hello world” message?

**Answers**:

- Eduarda Gervini Centeno: docker run alpine echo "hello-world"
- Haili Hu: `docker run alpine echo "Hello world"`
- Harikrishnan Vijayakumaran: `docker run alphine echo "Hello World"`
- Hédia Tnani:`docker run alpine echo 'Hello world'
- Izzy Hendriks: `docker run alpine echo 'hello world' `
- Jairus Beije: `docker run alpine echo 'Hello World'`
- Leonardo Honfi Camilo: `docker run alpine echo "hello world"`
- Malbert Rogers: `sudo docker run alpine echo "Hello world"`
- Manuel Cardosa: `docker run alpine echo 'Hello, World!'`
- Marianna Avetisyan: 
- michela busana: `sudo  docker run alpine echo 'hello-world'`
- Mohamed Taoufik Tekaya:
- Parisa Zahedi:docker run alpine echo "Hello world"
- Richard van Dijk: see below
```
PS C:\Users\richa> docker run hello-world echo "HELLO"
docker: Error response from daemon: OCI runtime create failed: container_linux.go:380: starting container process caused: exec: "echo": executable file not found in $PATH: unknown.
PS C:\Users\richa> docker run alpine echo "HELLO"
HELLO
```
- Shashank Shekhar Harivyasi: `docker run alpine echo "hello world"`
- Shengnan Liu: `docker run alphine echo 'Hello world!'`
- Tijmen Molema: `sudo docker run alpine echo "hello world"
- Xiaoming Tian: `docker run alpine echo 'hello world!'`
- Franciso Regateiro: docker run alpine echo "Hello World"


**Solution**:

```
$ docker run alpine echo "Hello World"
```

### Exercise 7: Practice Makes Perfect
Use `docker search` to find out to see if your favorite linux distro is available as docker image. Then, start a container with that docker image and run the command `cat /etc/os-release` to find out the version of linux installed in that container.

If you don’t have a favorite linux distro, you can pick one of the following:

ubuntu
debian
fedora

**Answers**:

- Eduarda Gervini Centeno: docker run ubuntu cat /etc/os-release
- Haili Hu: `docker run ubuntu`
- Harikrishnan Vijayakumaran:`docker run ubuntu`
- Hédia Tnani:`docker run ubuntu`
- Izzy Hendriks: `docker run linuxmintd/mint20-amd64`
- Jairus Beije: `docker run -it fedora` + `cat /etc/os-release`
- Leonardo Honfi Camilo: `docker run -it ubuntu:21.04 /bin/bash`
- Malbert Rogers: `sudo docker run centos cat /etc/os-release `
- Manuel Cardosa: `docker run -it archlinux:latest bash`
- Marianna Avetisyan: `sudo docker run ubuntu cat /etc/os-release`
- michela busana: `sudo docker run centos cat /etc/os-release`
- Mohamed Taoufik TEKAYA:
- Parisa Zahedi`docker run ubuntu cat /etc/os-release`
- Richard van Dijk: see below
```
PS C:\Users\richa> docker run ubuntu cat /etc/os-release
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
35807b77a593: Already exists
Digest: sha256:9d6a8699fb5c9c39cf08a0871bd6219f0400981c570894cd8cbea30d3424a31f
Status: Downloaded newer image for ubuntu:latest
NAME="Ubuntu"
VERSION="20.04.3 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.3 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: `docker run ubuntu`
- Shengnan Liu: docker pull miniconda-cuda -> Request denied...
- Tijmen Molema: `sudo docker run kalilinux/kali-rolling`
- Xiaoming Tian: `docker run ubuntu`
- Franciso Regateiro:NAME="Ubuntu" VERSION="20.04.3 LTS (Focal Fossa)"

**Solution**:
```
$ docker search debian
$ docker run debian cat /etc/os-release
```

### Exercise 8: What’s in a name?
How would I download the Docker container produced by the `rocker` group that has version 3.6.1 of R and the tidyverse installed?

**Answers**:

- Eduarda Gervini Centeno: `docker pull rocker/tidyverse:3.6.1`
- Haili Hu:`docker pull rocker/tidyverse:3.6.1`
- Harikrishnan Vijayakumaran:
- Hédia Tnani:`docker pull rocker/tidyverse:3.6.1`
- Izzy Hendriks: `docker pull rocker/tidyverse:3.6.1`
- Jairus Beije: `docker pull rocker/tidyverse:3.6.1`
- Leonardo Honfi Camilo:
- Malbert Rogers: `sudo docker pull rocker/tidyverse:3.6.1`
- Manuel Cardosa: `docker pull rocker/tidyverse:3.6.1`
- Marianna Avetisyan: `docker pull rocker/tidyverse:3.6.1`
- michela busana: `sudo docker run rocker/tidyverse:3.6.1 ` 
- Mohamed Taoufik Tekaya:
- Parisa Zahedi`docker pull rocker/tidyverse:3.6.1`
- Richard van Dijk: see below
```
PS C:\Users\richa> docker pull "https://github.com/rocker-org/rocker-versioned:3.6.0"
invalid reference format
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: `docker pull rocker/tidyverse:3.6.1`
- Shengnan Liu: `docker pull rocker/tidyverse:3.6.1` 
???
```
docker pull gpuci/miniconda-cuda
Using default tag: latest
Error response from daemon: manifest for gpuci/miniconda-cuda:latest not found: manifest unknown: manifest unknown
```

- Tijmen Molema: `docker pull rocker/tidyverse:3.6.1`
- Xiaoming Tian: `docker pull rocker/tidyverse:3.6.1`
- Franciso Regateiro:docker pull rocker/tidyverse:3.6.1


**Solution:**
```
$ docker pull rocker/tidyverse:3.6.1
```

### Exercise 9: What container is right for you?

Find a Docker container that’s relevant to you. Take into account the suggestions above of what to look for as you evaluate options. If you’re unsuccessful in your search, or don’t know what to look for, you can use the R or Python containers we’ve already seen.

Once you find a container, use the skills from the previous episode to download the image and explore it.

**Answers**:

- Eduarda Gervini Centeno: `docker pull python`
- Haili Hu: `docker pull osgeo/gdal`
- Harikrishnan Vijayakumaran:
- Hédia Tnani:
- Izzy Hendriks: `docker pull continuumio/anaconda3`
- Jairus Beije: `docker pull mathworks/matlab`
- Leonardo Honfi Camilo: `docker pull python`
- Malbert Rogers: `sudo docker pull djbradshaw2/spades` -> `docker run -it djbradshaw2/spades bash` -> `spades.py --help`
- Manuel Cardosa: `docker run -it bitnami/pytorch`
- Marianna Avetisyan: 
- michela busana: `docker pull rcpp/ci`
- Mohamed Taoufik Tekaya:
- Parisa Zahedi:`docker pull elasticsearch`
- Richard van Dijk: 
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi:
- Shengnan Liu: 
- Tijmen Molema: `docker pull docker` (Not what I need, but I just found out i can run Docker in Docker which is wild)
- Xiaoming Tian: `docker pull python:3.6`
- Franciso Regateiro:

### Exercise 10: Take a Guess

Do you have any ideas about what we should use to fill in the sample Dockerfile to replicate the installation we did above?

**Answers**:

- Eduarda Gervini Centeno: done
- Haili Hu: done
- Harikrishnan Vijayakumaran:
- Hédia Tnani:
- Izzy Hendriks:  ok
- Jairus Beije: ok
- Leonardo Honfi Camilo: Yep, done.
    ```yaml
    FROM alpine
    RUN apk update
    RUN apk add --update python3 py3-pip python3-dev
    RUN pip3 install cython
    CMD ["python3", "-V"] 
    ```
- Malbert Rogers: I think so.
- Manuel Cardosa: 
    ```yaml
    FROM alpine
    RUN apk add --update python3 py3-pip python3-dev
    RUN pip install cython
    CMD ["python3", "--version"]
    ```
- Marianna Avetisyan: Python 3.9.5
- michela busana: yes
- Mohamed Taoufik Tekaya:
- Parisa Zahedi:
- Richard van Dijk: see below
```
FROM alpine
RUN install python3
RUN python --version
CMD ["ls","-l"]
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: done
- Shengnan Liu: 
- Tijmen Molema: I think I have it, but now not sure how to run my dockerFile
- Xiaoming Tian:
- Franciso Regateiro:

**Solution:**

```yaml
FROM alpine
RUN apk add --update python3 py3-pip python3-dev
RUN pip install cython
CMD ["python3", "--version"]
```

### Exercise 11: Exercise: Review!
1. Think back to earlier. What command can you run to check if your image was created successfully? (Hint: what command shows the images on your computer?)

2. We didn’t specify a tag for our image name. What tag did Docker automatically use?

3. What command will run the container you’ve created? What should happen by default if you run the container? Can you make it do something different, like print “hello world”?

**Answers**:

- Eduarda Gervini Centeno: done
- Haili Hu:1) `docker image ls` 2) latest 3) `docker run hailihu/alpine-python` (`docker run hailihu/alpine-python echo "hello world"`)
- Harikrishnan Vijayakumaran:
- Hédia Tnani:
- Izzy Hendriks: 1) `docker image ls` 2) latest 3) `docker run izzyknmi/alpine-python`. it will print `Python 3.9.5`. to change this, use `CMD ["echo","hello world"]`
- Jairus Beije: `docker image ls` , `docker run <name>`
- Leonardo Honfi Camilo:
    1. `docker image ls`, `docker inspect meh`
    2. latest
    3. `python3 -V`, yes
- Malbert Rogers: 1) `sudo docker image ls` 2) latest 3) `sudo docker run malbertr/alpin-python` Yes, change command next to CMD (`echo "Hello world"`) in the DockerFile
- Manuel Cardosa: 
- Marianna Avetisyan: 
- michela busana:
- Mohamed Taoufik Tekaya:
- Parisa Zahedi:
- Richard van Dijk: see below
```
1. > docker image ls
2. lastest
3. Change the Dockerfile and build it again

FROM alpine
RUN apk update
RUN apk add --update python3 py3-pip python3-dev
RUN pip3 install cython
RUN python3 --version
CMD ["echo","it works!!!"]

```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi:
- Shengnan Liu: 
- Tijmen Molema: ` Docker image ls || Latest || docker run tijmen/alpine-python || Default: print python version || Yes, change command text    OR run it with an echo command 
- Xiaoming Tian:
- Franciso Regateiro:docker image ls // latest // docker run / CMD ["echo", "Hello World!"]

**Solution**

1. `docker image ls`
2. `:latest`
3. Print the python version. To run another command:
```
$ docker run <NAME> echo "hello world"
```

## 🧠 Collaborative Notes

**containers**: self-contained, complete, separate computer file system.
**image**: a recipe for how to build a container


### Command log

**NOTE**: on Linux, you might have to add `sudo` to the commands

How to get help on docker commands:
```
$ docker --help
```

Get help for a specific command (e.g. build):
```
$ docker build --help
```

List all the images available on your computer (might be empty):
```
$ docker image ls
```

Download image to your computer:
```
$ docker pull hello-world
``` 

**Coffee Break**

Run docker container `hello-world`:
```
$ docker run hello-world
```
If the image is not available locally, `docker run` downloads the image first.

Check running containers:
```
$ docker container ls
```

Run the `alpine` container:
```
$ docker run alpine
```
Nothing happens. To run a command in the container:
```
$ docker run alpine cat /etc/os-release
```

Run a container interactively:
```
$ docker run -it alpine sh 
/ #
```
Type `exit` to exit and shut down the container or `Ctrl + d`.

Explore DockerHub website: https://hub.docker.com
For example, Python page: https://hub.docker.com/_/python 

Pull `python` image, version 3.8, use 'tag' 3.8 (i.e. add `:3.8`):
```
$ docker pull python:3.8
```
Default version is `:latest` (if tag is not specified). 

List all container images downloaded so far:
```
$ docker image ls 
```
Remove image using its ID or REPOSITORY name: 
```
$ docker image rm <ID>
```
You can't delete image if an associated container is still present! Check all containers (running, but also completed):
```
$ docker container ls --all
```
So, first remove the container:
```
$ docker container rm <CONTAINER ID>
```
then you can remove the image. 
To remove all (completed) containers:
```
$ docker container prune
# then press 'y'
```

**BREAK: back at 11:45**

Run the `alpine` container interactively, then install Python, then install some Python package  with `pip` (e.g. `cython`):
```
$ docker run -it alpine sh
#/ apk add --update python3 py3-pip python3-dev
#/ python3 --version
#/ pip install cython
```

Better solution: create image with Python and `cython` installed. Edit `Dockerfile` from downloaded files:
```
$ cd docker-intro/basic
$ nano Dockerfile  # or any other text editor
```
To build an image based on the Dockerfile (need):
```
$ docker build -t <USERNAME>/<CONTAINERNAME> .
```
To push image to DockerHub:
```
$ docker push <IMAGE NAME>
```

To rename (tag) a container:
```
$ docker tag <original-image-name> <new-image-name>
```


## 📚 Resources

Zoom link to meetup start today September 15th, 2.30pm,
https://us06web.zoom.us/j/88390257042?pwd=OTVKR0VVRHBLWVg4L0RhTUljbW1BZz09
For certificate of attendance email: 
training@esciencecenter.nl

## Tip (what can be improved) 
- installation check session could be done offline by ourselves with some instructions 
- chat client, please use something like slack, the zoom chat is very poor
- Agreed on the chat, it's hard to follow on zoom
- The reason/purpose of the commands we entered was not always clear to me
- I have to many screens open, chat, presentation, my CLI, docker images. Maybe we should use an diffrent chat? I also dislike zoom (it is unlogic) (seconded)
- for tomorrow the pace could be a bit faster (depending on everyone of course)
- please make notes in collaborative doc, from the most important notes that are mentioned during teaching.
- The pace during last hour went up therefore was difficult to keep up.

## Top (what went well)
- good balance between slides and hands-on exercises :+1: 
- Clear instructions and explanations, relaxed instructors.
- Nice pace for an introductory course
- Good intro
- I like the reminder for attending the setup session, which is very important.
- Nice/positive atmosphere
- This document really works to get a 'group feel', it makes me feel more connected with all other altough we're still home
- The collaborative document is very helpfull
- Very good examples, speed is slow but not boring (which is impressive!)
- Good, clear intructions and good mix of practice and theory
- well done, very good course.
- Hands-on excercises are great!
- Great atmosphere and agree on "Nice pace for an introductory course"
- Maybe comments can be added to the code lines so that it is clear what the purpose is