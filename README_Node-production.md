## Node production- Docker+AWS

# Lesson 1. Deploy to the Cloud

https://academy.zerotomastery.io/courses/1206554/lectures/33299692

# Lesson 2. Serveless vs Containers

https://academy.zerotomastery.io/courses/1206554/lectures/33236387

Deploy our app in a container (Docker)

# Lesson 3. Virtual machine

https://academy.zerotomastery.io/courses/1206554/lectures/33236390

# Lesson 4. What is a container

https://academy.zerotomastery.io/courses/1206554/lectures/33236392

# lesson 5. Installing Docker

https://academy.zerotomastery.io/courses/1206554/lectures/33302247

# Lesson 6. Our first Docker container

Run this in the terminal.:
docker run -d -p 80:80 docker/getting-started

We get this CLI by going to hub.docker.com and select docker/getting-start

Then in google:
localhost:80

It shows the images

# Lesson 7. Your docker account

https://academy.zerotomastery.io/courses/1206554/lectures/33236395

# Lesson 8. Creating a Docker file

https://academy.zerotomastery.io/courses/1206554/lectures/33302250

# Lesson 9. Improving our Ocker file with layer

https://academy.zerotomastery.io/courses/1206554/lectures/33302252

# Lesson 10. Updating our API URL

https://academy.zerotomastery.io/courses/1206554/lectures/33345540

N: In the Client we erase the localhost in the URL since we are running same server and just living v1
before:
const API_URL = 'http://localhost:8000/v1';
now:
const API_URL = 'v1';

# Lesson 11. Building NASA project Docker image

https://academy.zerotomastery.io/courses/1206554/lectures/33345262

CMD to build the image in Docker:

docker build . -t carlosinfante1980/nasa-project

Example:
docker build [options].

- We pass the location: space dot, which means current directory
- t carlosinfante1980/nasa-project. It is my name in docker (the same in github, since I signed up in Docker with my github account)
- /nasa-project. name of the project

# Lesson 12. Running NASA project in a container

https://academy.zerotomastery.io/courses/1206554/lectures/33315929

docker run -it -p:8000:8000 carlosinfante1980/nasa-project

# Lesson 13. Pushing image into Docker Hub

https://academy.zerotomastery.io/courses/1206554/lectures/33315930

docker push carlosinfante1980/nasa-project

# Lesson 14. Exploring Amazon Web Service

https://academy.zerotomastery.io/courses/1206554/lectures/33236397

# Lesson 15. Creating an EC2 Instance 1

https://academy.zerotomastery.io/courses/1206554/lectures/33344735

# Lesson 16. Creating an EC2 Instance 2: Security

https://academy.zerotomastery.io/courses/1206554/lectures/33320966

# Lesson 17. What is SSH?

https://academy.zerotomastery.io/courses/1206554/lectures/33236398

SSH stands for Security Shell

# Lesson 18. Connecting To Our EC2 Instance With SSH

https://academy.zerotomastery.io/courses/1206554/lectures/33345295

Just follow Amazon instructions

# Lesson 19. Setting Up Our EC2 Server

https://academy.zerotomastery.io/courses/1206554/lectures/33315729

LINUX terminal in Amazon:

1. Update yum
   sedu yum update -y

- yum is like npm. With this command we are making sure that is update. <sudo> means we run it as administrator.

2. Install docker
   sudo yum install docker

3. Start Docker
   sudo service docker start

4. Add user mod so we dont need to type sudo to execute a docker command
   sudo usermod -a -G docker ec2-user

5. Save changes of step 4. Need to log out and log in again
   5.1 - To Log out, Type: exit
   5.2 - To Log in, type the command gived by Amazon

# Lesson 20. Deploying Our NASA API

https://academy.zerotomastery.io/courses/1206554/lectures/33357910

docker run --restart=always -p 8000:8000 carlosinfante1980/nasa-project

The app is online!
http://16.16.201.72:8000/

16.16.201.72 I copy from my AWS where the EC2 nasa-project is been built
