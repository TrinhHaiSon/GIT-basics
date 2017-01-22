Recording changes to the repository
==================
#### 1. **Cloning an existing repository**

If you want to copy of an existing directory, the command you need is 'git clone'. Take a note that there is another command is 'git checkout'
and the difference between them is that while 'git checkout' allow you to get just a working copy, 'git clone' give you a full copy
of nearly full data that the server has. Every version of every file for the history of the project is pulled down by defaul when you
run 'git clone'.  
Example: ![alt-text](Imges/Screenshot from 2017-01-23 00-46-39.png)  
That creates a directory named Git-basics and, initializes a .git directory inside it, pulls down all the data for that directory and check out a working copy of the lastest version. If you want to clone the repository into a directory named somthing other than 'Git-basics', you can specify that as the next command-line option: 
![atl-text](Imges/Screenshot from 2017-01-23 01-02-41.png)  
Git uses a number of different protocols. The previous example uses https:// protocol but you can also see git:// or user@server:path/to/repo.git, which uses the SSH transfer protocol.

#### 2. **Tracked and Untracked**


