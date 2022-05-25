# How to run Jenkins example project

Once you get to the Jenkins home page, just click in ***create a new job***. Naming the job ***test-project*** and set it to be a ***Freestyle project***.

![create_test_project](/images/06_create_test_project.png)

Leave everything as default and add a new Shell Execution under Build. Add this as the command:

`echo "this is my first jenkins attempt and is working!!"`

![add_shell_command](/images/07_add_shell_command.png)

Save the job and go to the main screen, Click the ***Build Now*** button on the left-hand side to build the source code.

![build_button](/images/08_build_button.png)

After clicking on **Build now**, you can see the status of the build you run under Build History.

![build_history](/images/09_build_history.png)

Click on the build number and then Click on ***Console output*** to see the status of the build you ran. It should show you a success message, provided you have followed the setup properly as shown in the below Jenkins create new job example.

![console_output](/images/10_console_output.png)
