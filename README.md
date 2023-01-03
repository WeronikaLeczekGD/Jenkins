# Jenkins

1. [Install Jenkins according to documentation (Java based or docker based).](#ad-1)

2. [Make a base setup of Jenkins (User configuration, plugin installation)](#ad-2)

3. [Add a Dockerfile to your repository with spring-petclinic.](#ad-3)

4. [Create 2 docker repositories on your own Nexus Repository (Instruction) or https://hub.docker.com/ called “main” and “mr”.](#ad-4)

5. [Add Jenkinsfile and describe the following behavior there:](#ad-5)

## The pipeline for a merge request should include the following jobs:

1. Checkstyle

Use Maven or Gradle checkstyle plugin to generate a code style report. It should be available as a job artifact.

2. Test  (with Maven or Gradle)

3. Build

Build without tests (with Maven or Gradle).

4. Create a docker image

Using your Dockerfile in the spring-petclinic repo, create a docker image with spring-petclinic application,  tag it using GIT_COMMIT (short)  and push it to the “mr” repository.

Note: Pipelines should be executed in Jenkins agents

## The pipeline for the main branch should include the following job:

1.Create a docker image

Build a docker image and push it to the “main” repository.

Note: Pipelines should be executed in Jenkins agents

<br />
<br />

---
---

<br />
<br />


## Ad 1

### Instaling and starting Jenkins using commands below:

-Instaling:

```brew install jenkins-lts```

-Starting:

```brew services start jenkins-lts```

Note: When using launchctl the port will be 8080.

## Ad 2

Here I created an user and installed some docker and maven plugins

## Ad 3

I had added it in previous "Docker" topic:


## Ad 4

Creating 2 docker repositories on dockerhub:

![Screenshot 2023-01-03 at 19 08 41](https://user-images.githubusercontent.com/114099418/210415956-7949d92e-bf12-45b7-85df-59276676e3e9.png)

## Ad 5

### My Jenkinsfile for mr repository:

![Screenshot 2023-01-03 at 19 16 20](https://user-images.githubusercontent.com/114099418/210417088-491839a6-7a06-464c-946e-a36f5c864d6e.png)

Succelfull pipeline:

![Screenshot 2023-01-03 at 19 19 08](https://user-images.githubusercontent.com/114099418/210417547-c624c2a9-ba2b-48f8-8c4d-70cfdf0949ea.png)

### My Jenkinsfile_main for main repository:

![Screenshot 2023-01-03 at 19 17 38](https://user-images.githubusercontent.com/114099418/210417238-c8e0a997-d776-45ca-89d7-7fa87e3e9ed5.png)

Succelfull pipeline:

![Screenshot 2023-01-03 at 19 20 26](https://user-images.githubusercontent.com/114099418/210417676-7a0170a3-956d-40fe-a05e-4acdec3e6d3d.png)

My Credentials:

![Screenshot 2023-01-03 at 19 33 04](https://user-images.githubusercontent.com/114099418/210419644-b29ad80d-87a9-429b-b621-65d9ffc6d9f7.png)




