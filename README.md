# How to run NodeJS job in Jenkins

> **Important:** If you don't have a jenkins instance and you want to run jenkins in local you can visit this [link](./installJenkins.md).

Now, to run a **NodeJS** project in Jenkins please follow the next steps:

1. First of all, you will need to install the **NodeJS plugin** in Jenkins because it just supports java by default. ​​To do this, navigate to ***Manage Jenkins -> Manage Plugins*** and look for *NodeJS* and install the plugin.

    ![manage_jenkins](/images/11_manage_jenkins.png)

    ![install_nodejs_plugin](/images/12_install_nodejs_plugin.png)

    ---

2. When the installation is completed navigate to Manage ***Jenkins -> Global Tool Configuration*** and look for the **NodeJS** heading. Install whatever version of NodeJS you require and click save:

    ![configure_nodejs_version](/images/13_configure_nodejs_version.png)

    ---

3. Now we must create a NodeJS job with npm scripts. Naming the job ***nodejs-project*** and set it to be a ***Freestyle project***:

    ![create_nodejs_project](/images/14_create_nodejs_project.png)

    Under **Source Code Management**, Enter your repository URL. We have a test repository located at <https://github.com/jersonlopez/nodejs-jenkins.git> Make sure you choose the right branch.

    ![add_repository](/images/15_add_repository.png)

    If it is a private repository you can add the **credentials** in the credentials options. There are several options to log in to a private repository, you can choose the one which is suitable to you.

    ![credentials](/images/16_credentials.png)

    Under **Build Environment**, Select the name of the Node installation we just created:

    ![set_nodejs_build](/images/17_set_nodejs_build.png)

    > **Important:** If your project uses environment variables you can visit this [link](./envVariables.md) to know how to setting up them.

    Now go to the **Build** heading, choose a ***Execute shell*** and add the following:

    ![add_nodejs_commands](/images/18_add_nodejs_commands.png)

    Save the job and go to the main screen again, Click the ***Build Now*** button. After clicking you can see the status of the build you run under **Build History**. Click on the build number and then Click on **Console output** to see the status of the build you ran. It should show you a success message.

    ![nodejs_console_output](/images/19_nodejs_console_output.png)
