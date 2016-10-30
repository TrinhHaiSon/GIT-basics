What is Git?
=============

> ### Definition
GIT is the free and open source distributed version control system designed to handle from small to very large projects with speed
and efficiency

In another words, Git is the software that keeps track of changes that you made to files and directories. It's specially good to
keep track of text change that you made. Let imagine that you have a document, you have version 1 of that document, you make some changes
to it. Now you have version 2. You make more changes, and you get version 3. GIT keeps track of those 3 different versions for you and it
allows you to move back and forth to compare them and to see what changes between each one.

> ### Version Control System (VCS)

There are five most important and influential Version Control System that I'll talk about

#### 1. **Source Code Control System (SCCS)**
SCCS isn't the first VCS that's ever made but it's the first one that became popular. SCCS is released in 1972, developed by 
AT&T and bundled free with Unix. Before SCCS came out VCS had something like a budget in which you might save version 1, version 2,
version3,...(just giving different file names each time). When you do that, you're actually saving the full document three different
times which isn't the most efficient way to do. What SCCS does is keeping the original document and then instead of saving the whole
document in the second time it just saves the snapshot of what the changes were. So if you want version 5 of the document you just take
version 1 and apply 4 sets of changes. It's the more efficient way to store the changes over time.

#### 2. **Revision Control System (RCS)**
SCCS stays dominant until the early 1980s when RCS was developed. It just make lots of improvements over SCCS. One of them is
cross-platform whereas SCCS is for Unix only. With the rise of personal computer, it's important to have a VCS that works on PCs. RCS
is also more intuitive, has a cleaner syntax with fewer commands but more features and most importantly, it's faster. Lots of it's speed
increase came from the fact that it uses the smarter storage format. While SCCS stores it's original file and then keeps track of all the
changes that went after it, RCS flip that around so it keeps the most rencent file of whole form. If you want the previous versions, you just
apply the change snapshots to go backward in time. It's much faster because most of the time what we work with is the current document. With 
SCCS, if we want the current document and there are 20 sets of changes, we have to pull up the original file and apply 20 sets of changes to get there. With
RCS we just bring up the original file and it's already stored in its full state.

#### 3. **Concurrent Version System (CVS)**
One of the problems with both SCCS and RCS is that they just allow you to work with an indivisual, one at a time. You can track changes in a single file
but not in a set of files of whole project. CVS allows you to do that. The real innovation is that CVS not only allows you to work with multiple filesl, it
also creates a place where you store you code called a code repository. You put your code in a remote server and more than one user can work with the same
file at the same time. You can work concurrently. Therefore users are able to share their work and update their files with changes that other people had made
and place in the remote repository. 

#### 4. **Apache Subversion (SVN)**
The idea working with remote repository was further improved upon with SVN. SVN is faster than CVS and allows saving non-text file like image whereas CVS
can't do that. Most importantly, the biggest innovation for SVN is that it can track not just changes to files or to group of files
but actually track what happened in the directory as the whole. SVN watchs files in the directory and also takes a snapshot of the directory not just files.
It may seem like a little different but very important. In CVS we're talking about having revision seven of some file, in SVN we talk about some file as its appears
in revision seven. SVN could track the history of directories. For example, CVS has a hard time if you rename a file, SVN would track that change with no problem: you add
a file in the directory, you move the file, rename it... While CVS can update file one at a time before it comes to either apply or read back changes, SVN instead of doing a
transactional commit, it apply all of the changes that happened to the directory or none of them at all. The snapshot is bigger than just the indivisual file. It's the entire
directory, the entire set of changes that happened to the directory at one time.

#### 5. **Git**
SVN'd stayed the most important popular CVS for a long time before Git came out. But there is another VCS that I want to look at before that, BitKepper SCM. It's closed source, proprietary
source code management tool and developed by BitMover Inc.. That company owned it and sell it. However the community version was free and that version was used for source code management of the
Linux kernel from 2002 to 2005. It's controversial to use proprietary SCM for Linux which is open source project and no one owns it whereas SCM was owned by a company. Therefore lots of people objected
said what if they change the rules in the future, suddently we're going to be screwed because we're stuck using this company software. In April 2005 that prediction came true when the community version
stopped being free.

BitKeeper was never as popular as CVS or SVN but it's very important to the creation of Git because of its connection to Linux. In April 2005 when the community version stopped being free, that's the same
point at which Git was created by Linux Tovalds as the alternative for managing source code. Git is distributed version control like BitKeeper, also open source and free. It compatible with Unix-like systems (Linux, 
Mac OS X, Solaris), Windows and it's faster than the other source code mangement tools (100 times faster in some cases). Git has better safeguards built into it to guard against data
corruption. Git became a hit as people discovered the power of distributed version control and they get used to all of Git's features. Git's experienced an explosion in popularity. GitHub's launched in 2008 to
host Git source code repositories. In 2009, there were over 50,000 repositories with over 100,000 users. Just two years later in 2011, there were over 2 million repositories with over 1 million users.

> ### Distributed Version Control

As we know, before Git came out, there were four most popular VSC that're ever created: SCCS, RCS, CVS and SVN. All four of these use a central code repository model which is that
there's one central place where you store the master copy of your code and when you're working with your code, you check out the copy from the master repository, you work with it, make your changes and then you submit
those changes back to the central repository. Other users can also work from that repository and submit their changes. And it's up to us as users to keep up to date with whatever happening in that central code repository
to make sure that we pull down and update any changes that other people've made.

Git doesn't work that way. Git is distributed version control. Different users or teams of users maintain their own repositories instead of working from a central repository and the changes are stored as change sets or patches.
We focus on tracking changes, not version of the document. Now, that's a subtle difference. You may think that CVS and SVN track changes too. In fact, they don't, they track the changes that're taken to get from version to version
of the different files through the different states of a directory.Whereas Git really focus on these change sets and encapsulating a change set as a discrete unit. Then those change sets can be exchanged between repositories. We're
not trying to keep up to date with the lastest version of something, instead, the question is "Do we have a change set applied or not?".







