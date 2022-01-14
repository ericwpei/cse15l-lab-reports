# __Week 2 Lab Report__

I'll be showing you how to connect your computer remotely to one of the computers in the CSE lab, as well as certain useful commands you can run.
<br/> <br/>

## Steps Required:
* Installing VSCode
* Remotely Connecting
* Trying Some Commands
* Moving Files with `scp`
* Setting an SSH Key
* Optimizing Remote Running
<br/> <br/>

# Part 1 - Installing VSCode
First, I downloaded VSCode [here](https://code.visualstudio.com). In addition, I also download Java to ensure that VSCode worked. Everything was fairly straightforward, as I had no problems installing and using VSCode.
<br/> <br/>

![Image](Lab_Report_1_Part_1.png)

# Part 2 - Remotely Connecting
First, I went to the website below to find the name of my account:
<br/> <br/>
[https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php)
<br/> <br/>
Then, I opened a terminal in VSCode and typed in the command:
<br/> <br/>
`ssh cs15lwi22ado@ieng6.ucsd.edu`
<br/> <br/>
I typed `yes` when prompted, and then typed in my password for my account. After logging in, my terminal looked like this:
<br/> <br/>

![Image](Lab_Report_1_Part_2.png)

<br/> <br/>

# Part 3 - Trying Some Commands
In my VSCode terminal, I tried the commands `pwd` and `ls` while connected to the remote server. Then, I logged out using `exit` and tried the same commands on my client.
<br/> <br/>

![Image](Lab_Report_1_Part_3.png)

# Part 4 - Moving Files with scp
I copied a file on my client called `WhereAmI.java` over to the remote server with the command:
<br/> <br/>
`scp WhereAmI.java cs15lwi22ado@ieng6.ucsd.edu:~/`
<br/> <br/>
I ran `ls` while connected to the remote server, and I saw that `WhereAmI.java` had been successfully copied over. I was also able to run `WhereAmI.java` on the remote server.
<br/> <br/>

![Image](Lab_Report_1_Part_4.png)

# Part 5 - Setting an SSH Key
An `ssh` key allowed me to connect to the remote server without entering a password, making the process much faster. I did this by using the command:
<br/> <br/>
`ssh-keygen`
<br/> <br/>

![Image](Lab_Report_1_Part_51.png)

This created a pair of files (a public and private key). I then copied the _public_ key over to my account on the server. On the server, I typed:
<br/> <br/>
`mkdir .ssh`
<br/><br/>
Afterwards, I typed this command (on my client):
<br/> <br/>
`scp /Users/ericpei/.ssh/id_rsa.pub cs15lwi22ado@ieng6.ucsd.edu:~/.ssh/authorized_keys`
<br/> <br/>

![Image](Lab_Report_1_Part_52.png)

<br/>
After this, I was able to connect to the remote server without a password.

# Part 6 - Optimizing Remote Running
There were more efficient ways of running commands on the server. I typed in the command below on my client to list the files in the directory of the server (without connecting to the server):
<br/> <br/>
`ssh cs15lwi22ado@ieng6.ucsd.edu "ls"`
<br/> <br/>

![Image](Lab_Report_1_Part_6.png)

<br/>

That concludes the end of my lab report.
<br/> <br/>

[Go back to home page](https://ericwpei.github.io/cse15l-lab-reports/)