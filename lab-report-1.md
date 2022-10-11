# Installing VScode: 
- Step 1: Install VS Code by going to this site [vs code](https://code.visualstudio.com/) 
- Step 2: Follow the Instructions on the site. 
(I already had it downloaded so this step was easy)

![first image](VSC.png)

# Remotely Connecting:
- Step 1: On the visual studio code terminal, type "ssh" follwed by your account username and "@ieng6.ucsd.edu".
- Step 2: If prompted for password, enter it by using copy-paste of password (Mine is set up to log in automatically without password, if this is your first time logging in you will be prompted with a message, say yes to this message and press enter for the logged in server you often connect to and proceed to copy-paste password)

![second image](SSH.png)

# Trying Some Commands:
- Step 1: In order to try some commands, make sure you are in the terminal
- Step 2: after ssh-ing, you can try some commands in on your computer or remote computer (below are some examples of commands I used including cat, cp, and ls commands. The cat command stands for "concatenate" and is used to print the contents of one or more files, the cp command is usually used to copy a file in a git repository and this file can be placed somewhere else, the ls command stands for "list" and is used to list files and folders in the current directory

![third image](commands.png)

# Moving Files with scp:
- Step 1: Create a file and make sure to compile and run your file in Visual Studio Code. (my file is called WhereAmI.java)
![fourth image](file.png)
- Step 2: Now in your terminal from the directory you made your file run "scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/". "scp" or secure copy copies files from one computer to another.
- Step 3: reenter your password just like when you enter with ssh
- step 4: log in to ieng6 with ssh, use "ls" to list the files in your home directory. Now you can run and compile thise file in your ieng6 computer (you should expect to see the file you copied over when you have used the "ls" command in your home directory, remote machines will show files saved on the remote machine and the same applies for local machine, in my screenshot it is a bit tough to tell what these differences may look like since I used a TA account)
![fifth image](scp.png)

# Setting an SSH Key
- Step 1: from your local computer, simply type ssh-keygen into your terminal. From here you want to enter the file in which to save key. (mine is a bit different since I have already done this so I overwrote my key, the same idea is applied though). From here you want to continously press enter until all the info shows up.
![sixth image](SSH.png)
- Step 2: For brand new ieng6 accounts in cs15l since these are new accounts you will not have the .ssh folder so in this case the user must make it themselves before proceeding with future steps (if this does not apply to you, you can skip this step)
- Step 3: copy the public key to the .ssh directory of your account on the server. Log into ssh cs15lfa22xx and input your password.
- Step 4: now in your client type (client is your computer) "scp /Users/username/.ssh/id_rsa.pub cs15lfa22@ieng6xx.ucsd.edu:~/.ssh/authorized_keys" and you will input your password.
- Step 5: what we did here is we no longer need to type password when trying to ssh or scp on this client to server. So try this by loggin in with ssh.
![seventh image](password.png)

# Optimizing Remote Running
- Step 1: We want to make remote running more pleasant as it will make us more efficient and help us complete tasks in less steps. One example of this is, if we want to make a local edit to a file, I would have to make a local edit to WhereAmI.java (WhereAmI.java is the file I am usng as the example in screenshot)
- Step 2: Then I will compile and run this file using java and javac commands.
- Step 3: Next I would use scp in my terminal for the file I made an edit to along with the remote machine I want copy it to. (it would look something like this "scp WhereAmI.java cs15lfa22ob@ieng6.ucsd.edu:~/")
- Step 4: From there just use copy-paste and use the up arrow key on the non-client terminal to do the commands on the remote terminal.
(In the screenshot below I compiled and ran a file in the same line after making changes to the file, using the arrow key and compiling and running files on the same line using a "semi-colon" can make the remote running experience more efficient as shown in the screenshot)
![eighth image](OPRR.png)
