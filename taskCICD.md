<<demo.zip>>
So, this task about CORE of CI/CD. Draft is below. If it suitable for you, we could add more clarification points.

In general - students should demonstrate simple CI/CD process with the next scenario:

•	Push changes to the repository
•	Jenkins pull latest changes and build artifact
•	Jenkins upload artifact to Artifactory
•	Jenkins triggering deployment of CI environment
•	As options - we should have possibility to deployment QA environment with the latest artifact on demand

Requirements: GitHub account, 3 vm - DevTools, CI env, QA env

Step 1: Put the code on GitHub

Login to GitHub (or get an account first if you don’t have one already) and create a new public repository with the some name. Upload demo project to public repository.

Step 2: Install CI/CD tools

Install on virtual machine Java, Maven, Git, Jenkins, Artifactory, Ansible …

Step 2: Configure CI/CD tools

Artifactory - create repository for build artifacts. Also, we'll use this repo for deployment procedure.

Jenkins - install required plugin, create build flow with the next steps - pull, build, upload. In this case you could use classic build flow or declarative pipeline. Create deployment jobs for CI and QA env. Don't forget, build flow should triggering when build flow is green.



How to build - mvn clean install

As options, you could take the tests in a separate step

Step 3: Configure Ansible

Create deployment role and role for initial provisioning (install java, add system user, create folders, etc ..)

How to run application - java -jar ./target/demo-0.0.1-SNAPSHOT.jar

Result you could see on http://<hostname>:8080

Step 4: Buld/Deploy flow improvement 

•	Add Better Code Hub (https://bettercodehub.com) to build flow
•	Containerize app with Docker for the build and deployment flow
•	Rewrite build flow to Jenkins pipeline (Groovy DSL)
•	Add possibility to choice version of artifact during deployment. In simple - it could be common string field. Advanced - drop down menu with artifacts list
