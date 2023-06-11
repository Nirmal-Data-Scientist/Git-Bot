# Gitbot

GitBot is a PowerShell script designed to automate common Git operations and simplify your Git workflows in Windows OS.

## User Guide

### Initial Setup

1. Ensure that you have PowerShell or Command prompt installed on your system.

2. Clone the GitBot repository to your local machine using the following command after navigating to the directory of your choice:

   ```
   git clone https://github.com/perjo927/gitbot.git
   ```
3. Create a new empty repository in github and clone that too. 

4. Move the `words.txt` file to the newly created GitBot repository folder and make sure you commit it to the remote repository. This file is used by GitBot to generate random names for branches and commit messages.

### Customization

1. Open the `gitbot.ps1` script in a text editor of your choice.

2. Modify the script as needed to customize its behavior. You can change the default branch name, or add additional functionality.

   - To change the default branch name, locate the line `Set-Location -Path $path` and replace `master` with your desired branch name.

   - Feel free to explore the script and customize it according to your specific requirements.

3. Save the modified script.

4. Open the `schedule_task.ps1` script in a text editor.

5. Modify the `$trigger` variable to adjust the desired schedule. By default, it is set to trigger the GitBot script daily at 6 PM. You can customize the schedule by modifying this variable.

6. Save the modified script.


### Execution

1. Open a PowerShell terminal or Command prompt Window and navigate to the `GitBot repository folder`.

2. Execute the GitBot script using the following command:

   ```
   powershell -ExecutionPolicy Bypass -File gitbot.ps1 -path <path-to-your-repo>
   ```

   Replace `<path-to-your-repo>` with the path to your target repository which you have newly created and has words.txt in it. This will initialize the GitBot process.

3. GitBot will create a new branch with a random name based on the words in the `words.txt` file, add a JavaScript file with content, commit the changes, push them to the repository, merge the branch into the default branch, and clean up the branch.

4. Repeat step 2 as needed to run GitBot manually.

### Scheduling

1. Open a PowerShell terminal or Command prompt window and navigate to the `GitBot repository folder` again.

2. Execute the `schedule_task.ps1` script using the following command:

   ```
   powershell -ExecutionPolicy Bypass -File schedule_task.ps1 -path <path to gitbot.ps1>
   ```
   
   Replace `<path-to-your-repo>` with the path to the directory where `gitbot.ps1` is present.

   This will create a scheduled task in Windows Task Scheduler, triggering the GitBot script based on the configured schedule.

3. Repeat the above 2 steps if you want to reschedule the GitBot process.

That's it! You have successfully set up and used GitBot to automate your Git workflows.

Feel free to explore the script and customize it further to suit your specific requirements. If you encounter any issues or have any questions, please refer to the GitBot repository for additional documentation or open an issue for support.

Happy GitBotting!
