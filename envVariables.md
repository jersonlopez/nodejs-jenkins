# How to use env variables in Jenkins

1. You will need to install the **Environment injector** plugin in Jenkins because it just supports java by default. ​​To do this, navigate to ***Manage Jenkins -> Manage Plugins***

    ![manage_jenkins](/images/11_manage_jenkins.png)

    Looking for *Environment injector* and install the plugin.

    ![manage_jenkins](/images/20_install_environment_plugin.png)

2. When the installation is completed navigate to your job **Configure** screen and set all environment variables you require under **Build Environment** and click save:

    ![manage_jenkins](/images/21_add_environment_var.png)

Now, yo have you environment variables ready to use them in your project.
