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

Each file in your working directory can be in one of two states: tracked or untracked. Tracked files are files in the last snapshot. They can be unmodified, modified or staged. Untracked files are everything else - any files in your working directory that was not in the last snapshot and are not in the staging area. When you first clone a directory, every files in it is tracked and unmodified because Git checked them out and you haven't editted anything.  
![alt-text](Imges/Screenshot from 2017-01-23 16-58-44.png)  

#### 3. **Checking the status for your file**

The main tool you use to check which file is in which state is 'git status' command. If you run that command directly right after a clone you'll see something like this:  
![alt-text](Imges/Screenshot from 2017-01-23 17-06-57.png)  
This means that you have a clean directory - in other word, there are no untracked and modified files.  
Now, you add a new file to your project, suppose that a file named README, then run the 'git status' c:  
![atl-text](Imges/Screenshot from 2017-01-23 17-23-12.png)  

You  can  see  that  your  new  README  file  is  untracked,  because  it’s  under  the
“Untracked  files”  heading  in  your  status  output.  Untracked  basically  meansthat Git sees a file you didn’t have in the previous snapshot (commit); Git won’t start including it in your commit snapshots until you explicitly tell it to do so. It
does  this  so  you  don’t  accidentally  begin  including  generated  binary  files  orother files that you did not mean to include. You do want to start including RE-ADME, so let’s start tracking the file.  

In order to begin tracking a new file, you use the command git add. To begin tracking the README file, you can run this:  
![alt-text](Imges/Screenshot from 2017-01-23 23-05-12.png)  
If you run your status command again, you can see that your README file is now tracked and staged to be committed:  
![alt-text](Imges/Screenshot from 2017-01-23 23-12-21.png)  
You  can  tell  that  it’s  staged  because  it’s  under  the  “Changes  to  be  committed” heading. If you commit at this point, the version of the file at the time you ran 'git add' is what will be in the historical snapshot. You may recall that when
you ran git init earlier, you then ran git add (files) – that was to begin tracking  files  in  your  directory. The git add  command  takes  a  path  name  for either  a  file  or  a  directory;  if  it’s  a  directory,  the  command  adds  all  the  files  in that directory recursively.  

#### 4. **Staging Modified Files**
Let’s change a file that was already tracked. If you change a previously tracked file called README.md and then run your git status command again, you get something that looks like this:
![alt-text](Imges/Screenshot from 2017-01-23 23-48-07.png)  
The README.md file  appears  under  a  section  named  “Changes  not staged for commit” – which means that a file that is tracked has been modified in  the  working  directory  but  not  yet  staged.  To  stage  it,  you  run  the git add command. 
git add is a multipurpose command – you use it to begin tracking new  files,  to  stage  files,  and  to  do  other  things  like  marking  merge-conflicted files as resolved. It may be helpful to think of it more as “add this content to the next commit” rather than “add this file to the project”.  Let’s run git add now to stage the 
README.md file, and then run git status again:
