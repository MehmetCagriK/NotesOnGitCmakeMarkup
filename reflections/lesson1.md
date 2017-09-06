# WHY TO USE VERSION CONTROL SYSTEMS

Version Control systems are used to save different versions of files as they 
change through time. VC systems allow us to restore older versions of files
or compare them between different versions.VC systems also optimizes storage
of these versioned files so they are not same as saving each versions of the 
files as they are in seperate directories. They save difference between 
files.

## Diff Command and Usage
  diff: This command allows us to compare two different files and show 
  differences. Example usage is like this

```bash
  diff game_old.js game_new.js
```

And the output of diff looks like this

```bash
  7d6
  <   13: 'enter',
  9a9
  >   38: 'up',
  395c395
  <     if (KEY_STATUS.spacr) {
  ---
  >     if (KEY_STATUS.up) {
  409c409
  <     if (KEY_STATUS.enter) {
  ---
  >     if (KEY_STATUS.space) {
  922c922
  <         KEY_STATUS.space = false; // hack so we don't move right away
  ---
  >         KEY_STATUS.space = false; // hack so we don't shoot right away
```

**Note:** I do not understand how to extract information from the text block
above.  But I will update this note later when I understood analyzing diff
text.

**QUESTION 1:**
How could having easy access to the entire history of a file make you 
a more efficient programmer in the long term?
**ANSWER:**
Being able to access history of a file allows to remember certain decisions
if these are also supported by documentation(commenting in source code etc).
It also helps to find the reason for suddenly malfunctioning program by 
reverting back to working versions.Once we recognize the fault injecting 
version; it is easy to find and fix the source with the `diff` tool.

## When to Commit
Git VCS has commits which are used to save changes made to the current version
of the file. Git commits are suggested to be small, easier to understand piece 
of changes. Each commit should represent a logical change.
To commit a file or files, follow the sequence below
  1. Save changes to files who are changed
  2. Add the files to staging are;

     ```bash
       git add <filename>
     ```

     Staging area is a region where the files are held before they are 
    committed.
  3. Commit the files;

      ```bash
       git commit
     ```

     Note that files that are not in the staging area are not committed.
     Note: The note above is simply false and misleading, Git commits files
     regardless of them being in staging area or not. But the purpose of 
     staging area is choosing which changes to commit. For example, if a file
     is updated but it is not put into staging area before commit, that update 
     will not be saved with that commit.

**QUESTION 2:**
Why do you think some version control systems, like Git, allow saving multiple
files in one commit, while others, like Google Docs, treat each file 
separately?
**ANSWER:**
Repository is a directory(collection of files and folders) under the 
responsibility of Git VCS when it is initialized as Git repository 
via git bash command;
  
  ```bash
    git init
  ```

Note that you need to change directory to the directory you want to be 
initialized as Git repository.

Git saves all files' current version in repository when there is a commit. The
reason why Git saves ALL files at once is those files are meaningful when
they are together. So committing only one file does not make any sense in
development point of view.

**QUESTION:**
How can you use the commands git log and git diff to view the history of files?
ANSWER:
When you use `git log` command(with optional parameters) you can see the commit
history of the repository. Commit history includes commit IDs which we can use
to identify commits in git diff command. Consider example output below

```bash
  $ git log

  commit 4e6648efa123e3c74caf4db31bd8f56ca6f3b5db
  Author: Cagri Kose <mehmetcagrikose@gmail.com>
  Date:   Sun Aug 27 12:40:33 2017 +0300

      Adding README.md.

  commit 5ab21b390588769ebf05cc2adc6d888ab4715aef (ZeroOrdering)
  Merge: 8c5ae16 a9864bc
  Author: Cagri Kose <mehmetcagrikose@gmail.com>
  Date:   Sat Aug 26 19:06:21 2017 +0300

  $ git diff 5ab2 4e66

  diff --git a/README.md b/README.md
  new file mode 100644
  index 0000000..399c3df
  --- /dev/null
  +++ b/README.md
  @@ -0,0 +1,5 @@
  +This workplace is created to hold files used for Git-GitHub classes of 
  +Udacity
  +in a version control system.
  +There is a <Reflection> directory under this directory. It includes a 
  +plaintext
  +file that contains reflections(thoughts on new information learned)
  +There is also <git.txt> file which is a sandbox for testing git system
```

## git checkout

Commits are snapshots are all files in the repository at the time of commit.
We can temporarily switch back to earlier commit, resetting the files to 
their older versions. This is called checkout.

```bash
  git checkout <commit_id>
```

**Note:** A Git commit ID is a SHA-1 hash of every important thing about the 
commit. Some of those things are
  1. The content, all of it, not just the diff.
  2. Commit date.
  3. Committer's name and email address.
  4. Log message.
  5. The ID of the previous commit(s).

This have three advantages according to StackOverflow answer;
  1. The system can tell if a commit has been tampered with.
  2. One can rapidly compare commits just by looking at their IDs.
  3. Two commits with the same IDs have the same history.

**QUESTION:**
How might using version control make you more confident to make changes that
could break something?
**ANSWER:**
With version control system we have many versions of the repository files saved
at different times. If we detect a bug in the program, we can revert to earlier 
commits incrementally to find in which commit the bug is introduced. Then we 
can fix the change that caused bug in a new commit.

**QUESTION**
Now that you have your workspace set up, what do you want to try using Git for?
**ANSWER**
First of all, I want to use Git in my personal project to enhance my knowledge
on Git. This will also help me to increase quality of my personal project. I 
will also the support suggestion of using Git on our workplace. Our current 
project is plagued with little to no documentation and giant commits of SVN.
Git will not magically solve our problems with version control of the new 
project but smaller commit policy of Git might be presented to peers and be
accepted by them. This way verification process will be far easier. A commit 
with thousand line change is really hard to verifiy.*RENT OVER*

## Example git diff Analyze

Below you will see how to analyze and read `git diff` output.

```bash
$ git diffcu 8c5a a986          ## Actually typed command
diff --git a/git.txt b/git.txt  ## Command reformatted by bash
index 1007de0..3e6a4ec 100644   
--- a/git.txt                   ## - denotes old file
+++ b/git.txt                   ## + denotes new file
@@ -1,4 +1,4 @@            
 This file is created for Git tutorials.
-Version Number: 1
-Does Kent Nelson wear the mask or does the mask wear Kent Nelson?
-Version Number: 2
+Version Info: 0
+I sacrificed everything. What have YOU given? -Edgy Demon Hunter, 2017
+Version Info: 1
```

`@@ -1,4 +1,4 @@` means 4 lines starting from 1st line of old file and 4 lines 
starting from 1st line of new file is shown below. Simply put "-/+ x,y" can be 
read like below;
  1. -/+ : Negative sign is prefix for old file and positive sign is prefix for
           updated file.
  2. x   : Starting line for the block
  3. y   : number of lines withing the block

Lines starting with - or + shows the lines that are deleted or added during 
change.

Note 1: "git diff ." command lists changes since last commit.
Note 2: "git diff abc123 def456" shows difference between abc123 as 
         old(not updated) version of repository and def456 as new(updated) 
	 version of repository

## git clone
This command copies repository into local storage with all its history.
But cloned repository is only local, meaning changes done on cloned repository
does not modify original repository directly.

## git commit
Initializing a repository to a Git repository does not commit anything.There 
are Couple reasons for this. First, user might not want to commit the files
in the repository at the time of initialization. Secondly, user would not be 
able to write a commit message if Git committed automatically.

