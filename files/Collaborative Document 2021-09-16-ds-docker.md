![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document

2021-09-16 Docker Introduction.

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: [link](https://tinyurl.com/dzw27zwj)

Collaborative Document day 1: [link](https://tinyurl.com/mfk4tpjk)

Collaborative Document day 2: [link](https://tinyurl.com/dzw27zwj)

Zoom link: https://us02web.zoom.us/j/85329504475?pwd=MUpxV2hEaUdGMHhJbkpXTGkwbzNNQT09

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

[link](https://esciencecenter-digital-skills.github.io/docker-introduction/files/docker-intro.zip) (NOW FIXED)

Post-workshop survey

[link](https://www.surveymonkey.com/r/5NV8YPK)

## 👩‍🏫👩‍💻🎓 Instructors

Djura Smits, Jens Wehner

## 🧑‍🙋 Helpers

Carlos Martinez Ortiz, Francesco Nattino

## Icebreaker
In the biopic of YOUR life, which actor should play you?
No need to be modest!

Jens: Craig Ferguson 
Tijmen: Eddie Redmayne (or john cleese?)
Izzy: Christina Hendricks
Leonardo: Leonardo DiCaprio
Djura: Phoebe Waller-Bridge
Haili: Michelle Yeoh
Shashank: Robin Williams (as in Dead Poets Society)
Jairus: Matthew Goode
Francesco: Woodie Allen :)
Malbert: Will Smith
Richard: 
Marianna: 
Carlos: Diego Luna 
Shengnan: Gong Li
Manuel: Bryan Cranston


## 🗓️ Agenda
| | |
|-|-|
|9:00|Welcome and icebreaker|
|9:15|Creating more complex container images|
|10:15|Coffee break|
|10:30|Practical examples |
|10:30|Containers and reproducibility|
|12:40|Wrap-up and survey|
|13:00|END|

## 🔧 Exercises

### Exercise 1: Explore the script
What happens if you use the docker run command `docker run -v ${PWD}:/icecream python python3 /icecream/sum.py` and put numbers after the script name?

- Eduarda : result is updated accordingly
- Haili Hu: numbers are summed
- Harikrishnan Vijayakumaran: returns the sum of all the numbers entered 1 2 3 4 => sum = 10
- Hédia Tnani:sum = 6
- Izzy Hendriks: sum.py 10 25 => sum = 35. yay
- Jairus Beije: sum.py 4 5 6 -> 15
- Leonardo Honfi Camilo: sum.py 1 2 5 : 8
- Malbert Rogers: Sums up the numbers (i.e. 25 40 100 returns `sum = 165`)
- Marianna Avetisyan: 
- michela busana: returns sum 
- Parisa Zahedi:sum.py 3 4 => sum = 7
- Xiaoming Tian: sum.py 11 12 -> 23
- Richard van Dijk: 
```
PS C:\eScience\docker-intro\docker-intro\sum> docker run -v ${PWD}:/temp python python3 /temp/sum.py 2 3
sum = 5
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: `sum.py 2 5 4; sum = 11`
- Shengnan Liu: `sum.py 9 7 8` sum=24
- Tijmen Molema: Some amazing calculating magic with only +- 50 MB ;)
- Manuel: Done --> sum.py 100 -4 = 96
- Marianna: docker run -v %cd%:/temp python python3 temp/sum.py 1 2 3 4 {=10}

**Solution**:
```
docker run -v ${PWD}/icecream python python3 /icecream/sum.py 1 2 3
```

### Exercise 2: Checking the options
Our Docker command (`docker run -v ${PWD}:/temp python python3 /temp/sum.py`) has gotten much longer! Can you go through each piece of the Docker command above the explain what it does? How would you characterize the key components of a Docker command?
- Manuel: Run python container with current directory mounted as volumen /temp. Then interpret script sum.py.
- Eduarda Gervini Centeno: -v is the mount volume, -w is working dir
- Haili Hu: `run`: run a docker container, `-v` mount a local folder (`$PWD`) to docker container (named `/temp`), `python`: docker image, `python3 /temp/sum.py`: command to run inside docker container
- Harikrishnan Vijayakumaran: docker runs python 3 in python docker container while mounting ${PWD} as temp, to execute the sum.py script. The numbers are the input arguments to the sum.py
- Hédia Tnani:
- Izzy Hendriks: `-v` mounts the local directory inside the docker container (e.g. `/temp/`), `-w` indicates the working directory in the docker container (should be the same as indicated after the `:` in the `-v` argument), `python` indicates the image used, `python3 sum.py 10 20` is the command to run inside the container to run the python script.
- Jairus Beije: start the container, link a local folder to the container, run python (specifically python3) and then run your script with several input numbers
- Leonardo Honfi Camilo: `-v` links a local folder into another folder inside the container, it stands for volume.  
- Malbert Rogers: `docker run` --> start container; `-v` mount this host folder (`$PWD/temp`) inside the container, using the image `python`, run the command `python3 /temp/sum.py` 
- Marianna Avetisyan: Creating a mount between our computer and the running container by means of using substitute '%cd%:/temp' to our current working directory
- michela busana: `-w` points to the wd; `-v` mounts the directory; `python` loads the dockerfile for python; the rest runs the script
- Parisa Zahedi:mount a volume to a docker container and run a python script inside that.
- Xiaoming Tian: `docker run` : run the container
- Richard van Dijk: run the image python, mount the volume, run the sum.py script with python3
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: call docker; start a (python:latest) container; mount PWD as a volume; start python 3; execute the script.
- Shengnan Liu: 
- Tijmen Molema: [program] [run] --> start a container[-v] load from the host machine the dir (command) PWD (which is home)and put it in /temp [python] the container name we want to [run], [python3 /temp/sum.py] start python3 with script /temp/sum.py.


### Exercise 3: Interactive jobs
Try using the directory mount option but run the container interactively. Can you find the folder that’s connected to your computer? What’s inside?

- Eduarda Gervini Centeno: docker run -v %cd%:/temp/ -it python sh .. then python3 /temp/sum.py
- Haili Hu: yes, same files as in local folder (Dockerfile, sum.py)
- Harikrishnan Vijayakumaran: :+1:
- Hédia Tnani:
- Izzy Hendriks: `docker run -it -w /izzy/ -v $PWD:/izzy python:slim sh` 
```bash=
# pwd
/izzy
# ls
Dockerfile  sum.py
# python3 sum.py 1 2 3
sum = 6
```
- Jairus Beije: `docker run -v ${PWD}:/tmp -it python sh`; `ls tmp` ; `python3 tmp/sum.py 4 5 6` -> 15
- Leonardo Honfi Camilo: `docker run -v $PWD:/meh -it python sh ; ls meh; cd meh; python3 sum.py 1 2 3; sum = 6`
- Malbert Rogers: `sudo docker run -it -v $PWD:/malbertr python bash, then with the command `ls` I can check for files/folders
- Marianna Avetisyan: 'docker run -it -v %cd%:/temp python bash', outcome [root@9ff0cbb94f08:/#], can see my temp directory there, it contains the Dockerfile and 'sum.py'
- michela busana: okay `sudo docker run -it -v $PWD:/michela  python bash` + `python3 sum.py 1 2 3`
- Parisa Zahedi: commands work for me
- Xiaoming Tian: `docker run -it -v %cd%:/test python bash` + `python3 /test/sum.py 1 2` -> 3
- Richard van Dijk: 
```
PS C:\eScience\docker-intro\docker-intro\sum> docker run -it -v ${PWD}:/temp python sh
# pwd
/
# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  temp  tmp  usr  var
# cd temp
# ls
Dockerfile  sum.py
# python3 sum.py 3 4
sum = 7
#

PS C:\eScience\docker-intro\docker-intro\sum> docker run -it -v ${PWD}:/temp python /temp/sum.py 2 3
sum = 5

This works without python3 executable? 

Answer: This is a configuration of this particular image python.
```
- Sebastian Costamagna:
- Manuel: 
`run -it -w /icecream/ -v $PWD:/icecream macardosa/sum-example bash`
`python sum.py 10 1 0` => sum = 11
- Shashank Shekhar Harivyasi: `docker run -it -w /exec -v $PWD:/exec python bash; python sum.py 2 3 4; sum = 9`
- Shengnan Liu: :+1: 
- Tijmen Molema: `sudo docker run -v $PWD:/icecream -it python sh`
                 `# cd icecream	
                 `ls
                    `Dockerfile  sum.py`

**Solution**
```
$ docker run -it -v $PWD:/icecream python bash
/# ls 
/# pwd
/# cd /icecream
/# ls
/# python sum.py 1 2 3
/# exit
```

Note: the `-v` links to the files outside the docker container. So files created in the `icecream` directory will also be available outside the container (even after the container is no longer running).

### Exercise 4: Did it work?
Can you remember how to run a container interactively? Try that with this one. Once inside, try running the Python script.

- Eduarda Gervini Centeno: yes
- Haili Hu: 
- Harikrishnan Vijayakumaran:
- Hédia Tnani:
- Izzy Hendriks: `docker run -it -w /izzy izzyknmi/python-sum sh` -> `ls`: `sum.py` -> `python sum.py 1 2 3`: `sum = 6`
- Jairus Beije: yes
- Leonardo Honfi Camilo: yep
- Malbert Rogers: Yes
- Marianna Avetisyan: 
- Manuel Cardosa: yes
- michela busana: yes
- Parisa Zahedi:yes
- Xiaoming Tian: 
- Richard van Dijk: 
```
PS C:\eScience\docker-intro\docker-intro\sum> docker run -it -v ${PWD}:/temp python:slim bash
root@9b4ae7b89d54:/# pwd
/
root@9b4ae7b89d54:/# cd temp
root@9b4ae7b89d54:/temp# ls
Dockerfile  chocolate.txt  sum.py
root@9b4ae7b89d54:/temp# cat Dockerfile
FROM python:slim
COPY sum.py /temp
CMD python3 temp/sum.py
root@9b4ae7b89d54:/temp#
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi:
- Shengnan Liu: 
- Tijmen Molema: Yes


### Exercise 5: Python Version Conflict
You are a social science researcher and are trying to establish how many people in a list are below the allowed drinking age. You are provided with a list of names and the corresponding birthdates.

A former PhD student already did the first part and wrote a program to convert birthdates into the current age of the people. Unfortunately it was written in Python2.7 and there is no way to upgrade it to Python3 (technically there is, but psssst).

As you are one of the best and brightest you have written a script to check the current age of people against the legal drinking age and output all people who are below it. You wrote it in Python 3.6. Your professor or boss and the rest of the group use python 3.3 in the work and cannot use your useful piece of software.

Create two docker containers and provide your colleagues with a working docker workflow.

Preparation work
Before you start with a solution, you need to download the files you need. They are available in `docker-into.zip`

the old script `docker-intro/versionconflict/convertbirthdaytoage.py` written by the former PhD in Python 2.7;
the new script `docker-intro/versionconflict/checkdrinkinglimit.py` you wrote in Python 3.6;
The `data docker-intro/versionconflict/data_birthday.csv` required for this study.
To simplify our workflow, let’s put them all in the same working directory:

~~~~bash
$ cd <your-working-directory>
$ ls .
checkdrinkinglimit.py  convertbirthdaytoage.py  data_birthday.csv
~~~~
You can first try to run them inside docker containers, afterwards try creating your own containers which nicely package this workflow. (Create one container for each file. You might want to look up the `ENTRYPOINT` instruction for the second task)

### Breakout room 1
Izzy, Hedia, Manuel

#### step 1: python 2.7

Dockerfile in folder py27:
```=
FROM python:2.7
COPY convertbirthdaytoage.py /
ENTRYPOINT ["python","/convertbirthdaytoage.py"]
CMD ["-h"]
```
to build: `docker build -t izzyknmi/birthday-2.7 .`

to run (from the folder where the birthdays CSV file is): `docker run -v $PWD:/birthday/ izzyknmi/birthday-2.7 -i /birthday/data_birthday.csv -o /birthday/data_birthday.json` 

output:
>Reading in csv file '/birthday/data_birthday.csv'
Writing to json file '/birthday/data_birthday.json'

now we have file: data_birthday.json!

#### step 2: python 3.6

Dockerfile in folder py36:
```=
FROM python:3.6
COPY checkdrinkinglimit.py /
ENTRYPOINT ["python","/checkdrinkinglimit.py"]
CMD ["-h"]
```
to build: `docker build -t izzyknmi/birthday-3.6 .`

to run (from the folder where the birthdays JSON file is): `docker run -v $PWD:/birthday/ izzyknmi/birthday-3.6 -i /birthday/data_birthday.json`

output:
>Reading in json file '/birthday/data_birthday.json'
Daria is not allowed to drink because they are only 6 years old!
Sherilyn is not allowed to drink because they are only 8 years old!
Clint is not allowed to drink because they are only 14 years old!
Val is not allowed to drink because they are only 13 years old!


### Breakout room 2

Two dockerfiles:
```
FROM python:2.7.18-slim
COPY convertbirthdaytoage.py /exec/
CMD python /exec/convertbirthdaytoage.py -i /exec/data_birthday.csv -o /exec/data_birthday.json
```
built as: `docker -v build -t harivyasi/birth .`
run as: `docker run -v $PWD:/exec harivyasi/birth`

```
FROM python:3.6.15-slim
COPY checkdrinkinglimit.py /exec/
CMD python /exec/checkdrinkinglimit.py -i /exec/data_birthday.json
```
built as: `docker -v build -t harivyasi/check .`
run as: `docker run -v $PWD:/exec harivyasi/check`



### Breakout room 3
Dockerfile 
      for python 2.FROM python:2.7




sudo docker run tijmen/python27 -v $PWD:/icecream -it bash
    Here we created output.json

OTHER OPTION:
Dockerfile:
    FROM python:2.7
    ENTRYPOINT ["python", "/icecream/convertbirthdaytoage.py"]
    CMD ["-i", "/icecream/data_birthday.csv", "-o", "/icecream/output.json"] 

sudo docker run tijmen/python27 -v $PWD:/icecream 
#### Dockerfile 2
Dockerfile2
    FROM python:3.6-slim
    ENTRYPOINT ["python", "/icecream/checkdrinkinglimit.py"]
    CMD ["-i", "/icecream/output.json"]
    
sudo docker run -v $PWD:/icecream tijmen/python36

Output:

    Reading in json file '/icecream/output.json'
    Daria is not allowed to drink because they are only 6 years old!
    Sherilyn is not allowed to drink because they are only 8 years old!
    Clint is not allowed to drink because they are only 14 years old!
    Val is not allowed to drink because they are only 13 years old!



ENTRYPOINT ["python", "/icecream/checkdrinkinglimit.py"]
CMD ["-i", "/icecream/output.json"]


    
### Breakout room 4
Dockerfile27
```
FROM python:2.7
COPY ./convertbirthdaytoage.py /temp/
ENTRYPOINT ["python2", "/temp/convertbirthdaytoage.py"]
```

Dockerfile36 
```
FROM python:3.6
COPY ./checkdrinkinglimit.py /temp/
ENTRYPOINT ["python3", "/temp/checkdrinkinglimit.py"]
```

build them
`docker build -t p27 -f Dockerfile27 .`
`docker build -t p36 -f Dockerfile36 .`

run them
`docker run -w /temp/ -v %cd%:/temp p27 -i data_birthday.csv -o test2.csv`
```
docker run -w /temp/ -v %cd%:/temp p36 -i test2.csv
```

output: 
> Daria is not allowed to drink because they are only 6 years old!
> Sherilyn is not allowed to drink because they are only 8 years old!
> Clint is not allowed to drink because they are only 14 years old!
> Val is not allowed to drink because they are only 13 years old!Daria is not allowed to drink because they are only 6 years old!
> Sherilyn is not allowed to drink because they are only 8 years old!
> Clint is not allowed to drink because they are only 14 years old!
> Val is not allowed to drink because they are only 13 years old!

#### Exercise 5:

How could Docker be useful for your research:

- Eduarda Gervini Centeno: transfer between python versions, 'fix' my software so that it's stable/sustainable after I leave my PhD
- Haili Hu: 1) I could use it to easier share my python projects with other people (now I ask them to install stuff with poetry for example). 2) I could use public docker images instead of installing stuff on my Mac, which gives problems sometimes 3) I can run my code quickly on a VM (e.g. Research Cloud)
- Harikrishnan Vijayakumaran: 1) Collaborative work with my project colleagues working on different platform. 2) I could make my work more accessible => good for the scientific reach of the project
- Hédia Tnani: Docker is very useful for me to build pipelines
- Izzy Hendriks: lots of dependencies and computers without internet access. can use this to make sure e.g. python comes along with the right libraries
- Jairus Beije: I can use it to create a self-contained package for any script/programs I used to publish alongside articles so that others can reproduce the results and efficiently use the methods for themselves.
- Leonardo Honfi Camilo: To use/modify/deploy applications, maybe together with podman/singularity for use in HPCs
- Malbert Rogers: Containerize pipelines on our department to make sure these are stable and results are reproducable.
- Marianna Avetisyan: At the University of Twente we are intending to advise Docker technology to containarize the research (software/output) in order to make it reproducible/sustainable and running at variouw architectures and especially in the long run. 
- Manuel Cardosa:
- michela busana: 
- Parisa Zahedi: In one of my projects, researchers need to install elasticsearch and kibana for their analysis. These softwares can be used via Docker container.
- Xiaoming Tian: sharing my package to the colleague who has different version of python
- Richard van Dijk: I like the virtualization aspects of Docker containers / images. Versioning of images is also interesting. I assist a number of PhD students asking questions about reproduciblity of their code.
- Shashank Shekhar Harivyasi: Sharing code and packages easily.
- Shengnan Liu: 
- Tijmen Molema: 
- Franciso Regateiro:



## 🧠 Collaborative Notes

Can you run `sum.py` example?

- Eduarda Gervini Centeno: yes
- Haili Hu: yes
- Harikrishnan Vijayakumaran: got it!
- Hédia Tnani:
- Izzy Hendriks: yup
- Jairus Beije: got it now, the alternative worked for me
- Leonardo Honfi Camilo: yep
- Malbert Rogers: Yes
- Marianna Avetisyan: I am lost, but i will take too much time to get me back at track, i will follow the collaborative notes later-- Yes!
- michela busana: yes
- Parisa Zahedi:yes
- Xiaoming Tian: yes
- Richard van Dijk: 
```
PS C:\eScience\docker-intro\docker-intro\sum> docker run -v ${PWD}:/icecream python python3 /icecream/sum.py 4
sum = 4
```
- Sebastian Costamagna:
- Shashank Shekhar Harivyasi: yes
- Shengnan Liu: :+1: 
- Tijmen Molema: Yahs

Meaning of some docker `run` options:
 `-v` -- stands for volume, mounts a volume inside the container.
 `-w` -- stands for working directory, indicates the working directory inside the docker image.
 `-i` -- runs interactively
 `-t` -- TTY, used in combination with `-i`
 
(Full list of options: https://docs.docker.com/engine/reference/commandline/run/)

### Command log

Try to run python script using Python from a container (won't work!): 
```
$ docker run python python3 sum.py
```

Mount volume to Docker container (make files accessible to the container):
```
# linux/Mac
$ docker run -v $PWD:/tmp python python3 /tmp/sum.py
# windows
$ docker run -v %cd%:/tmp python python3 /tmp/sum.py
```
Or alternatively:
```
# linux/Mac
$ docker run -w /tmp/ -v $PWD:/tmp python python3 sum.py
# windows
$ docker run -w /tmp/ -v %cd%:/tmp python python3 sum.py
```

Creating a file inside the container:
```
$ docker run -it -v $PWD:/icecream python bash
/# cd /icecream
/# touch chocolate.txt
/# exit
$ ls -l
```

** BREAK: back at 10:40 **

Including files in a docker image. Dockerfile:
```
FROM python:slim
COPY sum.py /icecream/
CMD python3 /icecream/sum.py
```

We build our docker image:
```
$ docker build -t djoerzilla/icecream .
```

A more complex dockerfile can run commands when the image is being built:
```
FROM python:slim
COPY sum.py /icecream/
RUN git clone https://github.com/dsmits/mycode
RUN wget ftp://ftp.server/dsmits/data.zip
RUN apk add python3
CMD python3 /icecream/sum.py
```
### Using entrypoints

We can turn our docker image into an executable by using ENTRYPOINT. Dockerfile:
```
FROM python:slim
COPY sum.py /icecream/
ENTRYPOINT ["python3" "/icecream/sum.py"]
CMD ["10", "10"]
```

We build our docker image:
```
$ docker build -t djoerzilla/icecream .
```
and we can run it:
```
$ docker run djoerzilla/icecream
```
**Output: sum = 20**

```
$ docker run djoerzilla/icecream 100 100
```
**Output: sum = 200**


## Feedback 

### Tops (what you liked)

- The slow but steady pace with explaining everything created a very safe and fine work environment
- hands-on exercises were the BEST
- I also like the teamwork for exercise
- nice to have an exercise with breakout rooms
- Practical 
- excellent teaching environment, really enjoyed the sessions
- Nice atmosphere, time for questions, good examples
- Amazing workshop. Very helpful inscructors and enand enand enand enand enand en
- Fun teachers! Very helpful!
- Handson session were really nice
- Good excercises that really hep with understanding the material
- Great, enthuasiastic instructors and helpers!
- Nice instructors, great hands-on excersises
- Enough material to read which in combination with the command log and help of experienced instructors ensures success of the learning process.

### Tips (what we can improve)
- more instructions for breakout sessions, we were in the beginning too shy to collaborate so just worked alone for a while
- I have no tip to make this better
- Zoom crashes in breakout rooms... not the best
- provide a readding list of sources
- more reference material - links to good example Dockerfiles etc.
- Some refrence material to read PRIOR to the course to get people up to speed
- Please stop using zoom (although they have a linux client)
- perhaps a bit more on dockerhub interaction and virtualization?
- I would love to see some more deep dive technical details.
- Maybe some more "real-world" examples Dockerfiles/images/containers (if they're not too advanced?)
- consider a part2 w more complex projects
- HackMD is very difficult to work with
- starting with exercises in teams so people open up more and switch on their camera's?
- Zoom was a bit difficult to use, maybe due to the fact that i was working on one computer screen.

## 📚 Resources

lectures notes: https://esciencecenter-digital-skills.github.io/docker-introduction/

zip location: https://esciencecenter-digital-skills.github.io/docker-introduction/files/docker-intro.zip
Post-workshop survey: https://www.surveymonkey.com/r/5NV8YPK

For certificate of attendance, please email: training@esciencecenter.nl
