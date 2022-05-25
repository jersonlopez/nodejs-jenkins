# How to run Jenkins in local

1. You should create a docker container running the following command:

    ```sh
    docker run -d --name jenkins-local -p 8082:8080 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
    ```

    If you were wondering what the arguments stand for, here is what each means:

    - d: detached mode
    - v: attach volume
    - p: assign port target
    - name: name of the container

    ==Important:== The argument `-v jenkins_home:/var/jenkins_home` creates a volume called `jenkins_home` if it does not already exist and mounts it under the path `/var/jenkins_home` inside the container. You'll notice that I am using port 8082 instead of the default 8080. The reason, other than demonstrating that you can use other ports, is that port 8080 is used by some web frameworks.

    If you run `docker ps`, you should see your docker container running

    ![docker_ps](/images/00_docker_ps.png)

    After confirming that your container is running, go to `localhost:<YOUR_PORT>` (localhost:8082 on my example) on your browser and you should see this page:

    ![unlock_jenkins](/images/01_unlock_jenkins.png)

2. Once in the browser, the initial admin password will be required to complete the Jenkins setup, which you can obtain by running the following command:

    ```sh
    docker exec jenkins-local sh -c "cat /var/jenkins_home/secrets/initialAdminPassword"
    ```

3. After copy the password and paste it on the webpage to unlock Jenkins. Click on Install suggested plugins on the Customize Jenkins page.

    ![getting_started](/images/02_getting_started.png)

    Wait until all plugins are installed and then you can proceed in creating your first admin user
  
    ![create_admin_user](/images/03_create_admin_user.png)

    After creating the admin user, setup the Instance configuration. Since you are only using Jenkins locally, leave the URL to your localhost URL. Click on Save and Finish to start using Jenkins.

    ![instance_configuration](/images/04_instance_configuration.png)

    And finally we have configured our Jenkins and now we can use it.

    ![welcome_jenkins](/images/05_welcome_jenkins.png)

To run your first example project visit this [link](./jenkinsExampleProject.md)
