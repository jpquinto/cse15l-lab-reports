# Lab Report 1
**Jeremy Quinto**

Hello future students (or me)! Welcome to my first lab report. In this report I will give a tutorial on how to login to a course-specific account on the remote server `ieng6`.

## Step 1: Installing VS Code
The first step to getting started is installing the wonderful IDE, VSCode.
Head  to this [link](https://code.visualstudio.com/download) in order to download VSCode. Your page should look like this:
![Install VDScode Site](installvscode.png)
Once you have VSCode installed and open, you are ready for the next step.

## Step 2: Remotely Connecting
For this class, you will have a course specific account from UCSD. Make sure you know your login and your password for that account so we can login to the server.
First, make sure you install [OpenSHH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
You can look up your course specific account [here](https://sdacs.ucsd.edu/~icc/index.php)

Now we will connect to the remote computer using VSCode's remote opton.

First, open a terminal in VSCode (`Terminal` in the top bar -> `New Terminal`). Then type the following command:
`$ ssh cse15lsp22zz@ieng6.ucsd.edu`
Make sure to replace the portion before "@ieng6" with your course specific username.
If asked if you want to continue connecting, type "yes" and hit enter.

If you've input your username correctly, you will be prompted to input your password (for super secret security reasons, your password won't show up when you type it, this is normal!). If you've entered your password correctly, youy terminal should look a little like this:
![Terminal Login](loginscreenshot.png)