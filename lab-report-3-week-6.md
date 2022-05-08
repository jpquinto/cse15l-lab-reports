# Lab Report 3
**Jeremy Quinto**

Hello again, future students (or me)! Welcome to my third lab report. In this report, we will be learning how to do a couple of things: 

1. Streamlining `ssh` configuration
2. Setting up GitHub Access from `ieng6`
3. Copying whole directories with `scp -r`
===
## Streamlining `ssh` Cnofiguration
To log onto the `ieng6` server from your desktop, you would type:
`ssh cs15lsp22zzz@ieng6.ucsd.edu`
This can be a lot to type every single time you're trying to log into the server. Luckily, we're going to streamline this!

To do this, we will add an entry in `~/.ssh/config` that tells SSH what username to use when logging into certain servers. 

In order to do this, on our remote desktop, follow these steps: 
1. Open up a Terminal
2. Create the `~/.ssh` directory if it doesn't exist:
    `mkdir -p ~/.ssh`
3. Go into the directory:
    `cd ~/.ssh`
4. We will now open the file `config` with the default editor:
    `open -t config`
    If it doesn't exist, create it with
    `touch config`
    and then try opening it again.
5. Finally, we will add the following lines to the file (make sure you're writing in Plain Text: **Format -> Make Plain Text**):
    ```
    Host ieng6
        HostName ieng6.ucsd.edu
        User cs15lsp22zzz (use your username)
    ```
*(I demonstrated these steps for Mac, but for other OS just open the `~/.ssh/config` file and follow step 5)*

This is what my terminal looked like when doing the steps above:
![](streamline-ssh-terminal.png)
And this is what my config file looked like after:
![](config-sc.png)

Next, run the command `ssh ieng6`, and if everything works, you should be logged in immediately, with no password! How easy!
![](streamlined-login.png)

If it doesn't work, try adding another line to the config file that explicitly refers to your `id_rsa` file (if you haven't made an `id_rsa` file, I explain how to do it in Lab Report 1):
```
Host ieng6
    HostName ieng6.ucsd.edu
    User cs15lsp22zzz (use your username)
    IdentityFile ~/.ssh/id_rsa
```

And there it is! Logging into the remote server is now a lot simpler! Great!

Now, as an example, I will demonstrate creating a secure copy onto the server with this streamlined approach.

Type `scp <file> ieng6` to copy a file. In this example, I copied `ToCopy.java`.
![](scp-streamlined.png)

===
## Setting Up GitHub Access From `ieng6`
In command-line `git`, we saw in class how to use `clone` and `pull` to get code from GitHub, and even `git status` to check the status. However, when we try and run `commit` and `push`
