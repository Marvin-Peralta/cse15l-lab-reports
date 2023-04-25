# **CSE15L Lab Report 1**

## by Marvin Peralta, A17271264

## **How to log into a course-specific account on 'ieng6'**

### **Step 1: Installing VSCode**

To install Visual Code Studio, you must go to [here](https://code.visualstudio.com/) and follow the instructions on how to download it to your device. Instructions will vary depending on whether you are using windows or mac so be careful! After installing, open up VSCode and the application should look something like the image below, depending on the color scheme.

![Image](VSCode_Startup.png) { height: 200px; }

### **Step 2: Remotely Connecting**

For opening up the terminal, if you are on windows you have to install git [here](https://gitforwindows.org) and set the default terminal "git bash" in VSCode through this [tutorial](https://stackoverflow.com/a/50527994), whereas if you are on a mac you can simply open up a terminal in  VSCode through the terminal menu at the top. Why do we need git in the first place? Well, since we are trying to connect to a system that other people can use, we need to use control system that tracks changes in the source code. Think of it as buying Xbox Live or Playstation Plus to play with your friends online!

Use the command:
`$ ssh cs15lsp23zz@ieng6.ucsd.edu`

Note that you should substitute zz to your own cse15l specific account. It will ask you if you want to connect, type 'yes' and type in your password for the account. Voila, you are connected! After typing your password, you should be presented with output like such:

![Image](Remote_Connection.png)

### **Step 3: Trying Some Commands**

Finally, you should run some commands to get a feeling of how much access you have. Commands like `cd`, `ls`, `pwd`, `mkdir`, and `cp` can be run on both your computer and the remote computer after using ssh that is.

Other specific commands you can try are:
* `cd ~` - which takes you back to home directory
* `cd` - which takes you to any directory so long as you add which directory afterwards (if not it takes you back to the home directory since there are no arguments)
* `ls -a` - which lists all the files, even hidden ones
* `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lsp23/cs15lsp23abc`, where the `abc` is someone else's account username - this command, when done right, lists the files in the directory that is appointed
* `cp /home/linux/ieng6/cs15lsp23/public/hello.txt ~/` - which copies the hello.txt file 
* `cat /home/linux/ieng6/cs15lsp23/public/hello.txt` - which prints out the contents of the hello.txt file

There are a variety of outputs but it is for you to explore. You can learn so much like me learning that you can use a basic `cat` command instead of an elaborate programming method to output text files! This is an example of a couple of inputs and outputs:

![Image](Commands.png)

And you can always log out of the remote server using:
* Ctrl-D
* Run the command `exit`
