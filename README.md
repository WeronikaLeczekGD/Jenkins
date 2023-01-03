# Jenkins


1. [Install Jenkins according to documentation (Java based or docker based).](ad-1)

2. [Make a base setup of Jenkins (User configuration, plugin installation).](ad-2)

3. [Add a Dockerfile to your repository with spring-petclinic.](ad-3)

4. Create 2 docker repositories on your own Nexus Repository (Instruction) or https://hub.docker.com/ called “main” and “mr”.

5. Add Jenkinsfile and describe the following behavior there:

The pipeline for a merge request should include the following jobs:

1.Checkstyle

Use Maven or Gradle checkstyle plugin to generate a code style report. It should be available as a job artifact.

2. Test  (with Maven or Gradle)

3. Build

Build without tests (with Maven or Gradle).

4. Create a docker image

Using your Dockerfile in the spring-petclinic repo, create a docker image with spring-petclinic application,  tag it using GIT_COMMIT (short)  and push it to the “mr” repository.

Note: Pipelines should be executed in Jenkins agents

The pipeline for the main branch should include the following job:

1.Create a docker image

Build a docker image and push it to the “main” repository.

Note: Pipelines should be executed in Jenkins agents


## Ad 1

### Instaling and starting Jenkins using commands below:

-Instaling:

```brew install jenkins-lts```

-Starting:

```brew services start jenkins-lts```

Note: When using launchctl the port will be 8080.


## Ad 2

Making a base setup of Jenkins (User configuration, plugin installation):

-User configuration:


## Ad 3

I had added it in previous "Docker" topic:


## Ad 4

Creating 2 docker repositories on your own Nexus Repository:


