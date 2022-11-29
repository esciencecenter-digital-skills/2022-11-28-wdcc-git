![](https://i.imgur.com/iywjz8s.png)


# 2022-11-28-wdcc-git Collaborative Document

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://tinyurl.com/wdcc-git

## 👮Code of Conduct

Participants are expected to follow these guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, just raise your hand.

If you need help from a helper, place an orange post-it note on your laptop lid. A helper will come to assist you as soon as possible.

## 🖥 Workshop website

https://esciencecenter-digital-skills.github.io/2022-11-28-wdcc-git/

🛠 Setup

https://esciencecenter-digital-skills.github.io/2022-11-28-wdcc-git/#setup

📈 Slides
https://ole.mn/2022-11-28-wddc-git

## 👩‍🏫👩‍💻🎓 Instructors

Sven van der Burg, Ole Mussmann

## 🧑‍🙋 Helpers

Makeda Candace Moore, Eva Viviani

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call


## 🗓️ Agenda
* 09:00	Welcome and icebreaker
* 09:30	Introduction to version control with Git
* 10:30	Coffee break
* 10:40	Tracking changes and exploring history
* 11:30	Coffee break
* 11:40	Ignoring things, remotes, and conflicts
* 12:30	Lunch
* 13:30	Centralized workflow with Git and GitLab
* 14:30	Coffee break
* 14:40	Distributed workflow with Git and GitLab
* 15:30	Coffee break
* 15:40	Distributed workflow with Git and GitLab
* 16:15	Wrap-up
* 16:30	Questions and discussions
* 17:00	END

## 🏢 Location logistics
* Coffee 
* Toilets ?
* **Wifi**: eduroam

## 🎓 Certificate of attendance
If you attend the full workshop you can request a certificate of attendance by emailing to training@esciencecenter.nl .

## 🔧 Exercises

## Exercise repository creation

### 1. Places to Create Git Repositories

Along with tracking information about planets (the project we have already created), Dracula would also like to track information about moons.
Despite Wolfman's concerns, Dracula creates a `moons` project inside his `planets` project with the following sequence of commands:

~~~
$ cd ~/Desktop   # return to Desktop directory
$ cd planets     # go into planets directory, which is already a Git repository
$ ls -a          # ensure the .git subdirectory is still present in the planets directory
$ mkdir moons    # make a subdirectory planets/moons
$ cd moons       # go into moons subdirectory
$ git init       # make the moons subdirectory a Git repository
$ ls -a          # ensure the .git subdirectory is present indicating we have created a new Git repository
~~~

Is the `git init` command, run inside the `moons` subdirectory, required for tracking files stored in the `moons` subdirectory?


### 2. (optional) Correcting `git init` Mistakes
Wolfman explains to Dracula how a nested repository is redundant and may cause confusion
down the road. Dracula would like to remove the nested repository. How can Dracula undo
his last `git init` in the `moons` subdirectory?

cd .. 
rm -rf .git
cd moons
git init

-Akankshya: rm  -rf .git


### Solution:

```
mkdir moons
cd moons
git init
ls -a #to check out what's inside the folder
```

Everything within the folder will be tracked automatically.

Let's try to remove .git:

```
rm .git
```

This will prompt: `rm: .git: is a directory`. This is a warning, so if you wish to remove a directory folder, type:

```
rm -rf .git 
```

`-rf` stands for **r**emove **f**orce.


### 1. Choosing a Commit Message

Which of the following commit messages would be most appropriate for the
last commit made to `mars.txt`?


1. "Changes"
2. "Added line 'But the Mummy will appreciate the lack of humidity' to mars.txt"
3. "Discuss effects of Mars' climate on the Mummy"

### Answers:

### 2. Committing Changes to Git

Which command(s) below would save the changes of `myfile.txt`
to my local Git repository?

1. 
~~~
$ git commit -m "my recent changes"
~~~
2.
~~~
$ git init myfile.txt
$ git commit -m "my recent changes"
~~~
3.
~~~
$ git add myfile.txt
$ git commit -m "my recent changes"
~~~
4.
~~~
$ git commit -m myfile.txt "my recent changes"
~~~




### Committing Multiple Files

The staging area can hold changes from any number of files
that you want to commit as a single snapshot.

1. Add some text to `mars.txt` noting your decision
to consider Venus as a base
2. Create a new file `venus.txt` with your initial thoughts
about Venus as a base for you and your friends
3. Add changes from both files to the staging area,
and commit those changes.

## Answers (type in your name when you're done)

Add changes to `mars.txt`:
```
nano mars.txt
```
Let's add another file:

```
nano venus.txt
```

We can add both files/changes, by tiping:

```
git add mars.txt venus.txt
```

To restore our files, before our changes:
```
git restore --staged mars.txt venus.txt
```

A shortcut to add everything at the same time:

```
git add .
```
This will also work:
```
git add *
```

However, it will add only non-hidden files. To add them anyway, but using the *:

```
git add * .*
```

However, at that point is simply easier to type `git add .`.

We commit now with a message
```
git commit -m "Write plans to start a base on Venus"
```


### (optional) `bio` Repository

* Create a new Git repository on your computer called `bio`.
* Write a three-line biography for yourself in a file called `me.txt`,
commit your changes
* Modify one line, add a fourth line
* Display the differences
between its updated state and its original state.




## Recovering Older Versions of a File

Jennifer has made changes to the Python script that she has been working on for weeks, and the
modifications she made this morning "broke" the script and it no longer runs. She has spent
~ 1hr trying to fix it, with no luck...

Luckily, she has been keeping track of her project's versions using Git! Which commands below will
let her recover the last committed version of her Python script called
`data_cruncher.py`?

1. `$ git checkout HEAD`

2. `$ git checkout HEAD data_cruncher.py`

3. `$ git checkout HEAD~1 data_cruncher.py`

4. `$ git checkout <unique ID of last commit> data_cruncher.py`

5. Both 2 and 4

## Answers

## Reverting a Commit

Jennifer is collaborating with colleagues on her Python script.  She
realizes her last commit to the project's repository contained an error, and
wants to undo it.  Jennifer wants to undo correctly so everyone in the project's
repository gets the correct change. The command `git revert [erroneous commit ID]` will create a
new commit that reverses the erroneous commit.

The command `git revert` is
different from `git checkout [commit ID]` because `git checkout` returns the
files not yet committed within the local repository to a previous state, whereas `git revert`
reverses changes committed to the local and project repositories.

Below are the right steps and explanations for Jennifer to use `git revert`,
what is the missing command?
1. `________ # Look at the git history of the project to find the commit ID`

2. Copy the ID (the first few characters of the ID, e.g. 0b1d055).

3. `git revert [commit ID]`

4. Type in the new commit message.

5. Save and close

## Answers

## Understanding Workflow and History

What is the output of the last command in

~~~
$ cd planets
$ echo "Venus is beautiful and full of love" > venus.txt
$ git add venus.txt
$ echo "Venus is too hot to be suitable as a base" >> venus.txt
$ git commit -m "Comment on Venus as an unsuitable base"
$ git checkout HEAD venus.txt
$ cat venus.txt #this will print the contents of venus.txt to the screen
~~~

1. ~~~
Venus is too hot to be suitable as a base
~~~
2. ~~~
Venus is beautiful and full of love
~~~
3. ~~~
Venus is beautiful and full of love
Venus is too hot to be suitable as a base
~~~
4. ~~~
Error because you have changed venus.txt without committing the changes
~~~

## Answers

## Checking Understanding of `git diff`

Consider this command: `git diff HEAD~9 mars.txt`. What do you predict this command
will do if you execute it? What happens when you do execute it? Why?

Try another command, `git diff [ID] mars.txt`, where [ID] is replaced with
the unique identifier for your most recent commit. What do you think will happen,
and what does happen?

## Answers

## Getting Rid of Staged Changes

`git checkout` can be used to restore a previous commit when unstaged changes have
been made, but will it also work for changes that have been staged but not committed?
Make a change to `mars.txt`, add that change, and use `git checkout` to see if
you can remove your change.

## Answers

## Explore and Summarize Histories

Exploring history is an important part of Git, and often it is a challenge to find
the right commit ID, especially if the commit is from several months ago.

Imagine the `planets` project has more than 50 files.
You would like to find a commit that modifies some specific text in `mars.txt`.
When you type `git log`, a very long list appeared.
How can you narrow down the search?

Recall that the `git diff` command allows us to explore one specific file,
e.g., `git diff mars.txt`. We can apply a similar idea here.

~~~
$ git log mars.txt
~~~

Unfortunately some of these commit messages are very ambiguous, e.g., `update files`.
How can you search through these files?

Both `git diff` and `git log` are very useful and they summarize a different part of the history
for you.
Is it possible to combine both? Let's try the following:

~~~
$ git log --patch mars.txt
~~~

You should get a long list of output, and you should be able to see both commit messages and
the difference between each commit.

Question: What does the following command do?

~~~
$ git log --patch HEAD~9 *.txt
~~~

## Answers

# Episode 06-ignore.md 

## Ignoring Nested Files

Given a directory structure that looks like:

~~~
results/data
results/plots
~~~

How would you ignore only `results/plots` and not `results/data`?

## Answers

## Including Specific Files

How would you ignore all `.dat` files in your root directory except for
`final.dat`?
Hint: Find out what `!` (the exclamation point operator) does

## Answers

## Ignoring Nested Files: Variation

Given a directory structure that looks similar to the earlier Nested Files
exercise, but with a slightly different directory structure:

~~~
results/data
results/images
results/plots
results/analysis
~~~

How would you ignore all of the contents in the results folder, but not `results/data`?

Hint: think a bit about how you created an exception with the `!` operator
before.

## Answers

## Ignoring all data Files in a Directory

Assuming you have an empty .gitignore file, and given a directory structure that looks like:

~~~
results/data/position/gps/a.dat
results/data/position/gps/b.dat
results/data/position/gps/c.dat
results/data/position/gps/info.txt
results/plots
~~~

What's the shortest `.gitignore` rule you could write to ignore all `.dat`
files in `result/data/position/gps`? Do not ignore the `info.txt`.

## Answers

## Ignoring all data Files in the repository

Let us assume you have many `.dat` files in different subdirectories of your repository.
For example, you might have:

~~~
results/a.dat
data/experiment_1/b.dat
data/experiment_2/c.dat
data/experiment_2/variation_1/d.dat
~~~

How do you ignore all the `.dat` files, without explicitly listing the names of the corresponding folders?

## Answers

## The Order of Rules

Given a `.gitignore` file with the following contents:

~~~
*.dat
!*.dat
~~~

What will be the result?

## Answers

## Log Files

You wrote a script that creates many intermediate log-files of the form `log_01`, `log_02`, `log_03`, etc.
You want to keep them but you do not want to track them through `git`.

1. Write **one** `.gitignore` entry that excludes files of the form `log_01`, `log_02`, etc.

2. Test your "ignore pattern" by creating some dummy files of the form `log_01`, etc.

3. You find that the file `log_01` is very important after all, add it to the tracked files without changing the `.gitignore` again.

4. Discuss with your neighbor what other types of files could reside in your directory that you do not want to track and thus would exclude via `.gitignore`.

## Answers

# Episode 07-github.md 

## GitHub GUI

Browse to your `planets` repository on GitHub.
Under the Code tab, find and click on the text that says "XX commits" (where "XX" is some number).
Hover over, and click on, the three buttons to the right of each commit.
What information can you gather/explore from these buttons?
How would you get that same information in the shell?

## Answers

## GitHub Timestamp

Create a remote repository on GitHub. Push the contents of your local
repository to the remote. Make changes to your local repository and push these
changes. Go to the repo you just created on GitHub and check the
[timestamps]({{ page.root }}{% link reference.md %}#timestamp) of the files. How does GitHub
record times, and why?

## Answers

## Push vs. Commit

In this episode, we introduced the "git push" command.
How is "git push" different from "git commit"?

## Answers

## GitHub License and README files

In this episode we learned about creating a remote repository on GitHub, but when you initialized
your GitHub repo, you didn't add a README.md or a license file. If you had, what do you think
would have happened when you tried to link your local and remote repositories?

## Answers

# Episode 09-conflict.md 

## Solving Conflicts that You Create

Clone the repository created by your instructor.
Add a new file to it,
and modify an existing file (your instructor will tell you which one).
When asked by your instructor,
pull her changes from the repository to create a conflict,
then resolve it.

## Answers

## Conflicts on Non-textual files

What does Git do
when there is a conflict in an image or some other non-textual file
that is stored in version control?

## Answers

## A Typical Work Session

You sit down at your computer to work on a shared project that is tracked in a
remote Git repository. During your work session, you take the following
actions, but not in this order:

- *Make changes* by appending the number `100` to a text file `numbers.txt`
- *Update remote* repository to match the local repository
- *Celebrate* your success with some fancy beverage(s)
- *Update local* repository to match the remote repository
- *Stage changes* to be committed
- *Commit changes* to the local repository

In what order should you perform these actions to minimize the chances of
conflicts? Put the commands above in order in the *action* column of the table
below. When you have the order right, see if you can write the corresponding
commands in the *command* column. A few steps are populated to get you
started.

|order|action . . . . . . . . . . |command . . . . . . . . . . |
|-----|---------------------------|----------------------------|
|1    |                           |                            |
|2    |                           | `echo 100 >> numbers.txt`  |
|3    |                           |                            |
|4    |                           |                            |
|5    |                           |                            |
|6    | Celebrate!                | `AFK`                      |

# Collaborative version control

## Exercise: Working as a project collaborator (in pairs):
Both of you should take the following actions:
- Log into GitLab and create a new repository
- Make the repository public
- clone it to your desktop
- add some code
- push the changes to the repository
- Add the other person as a collaborator.
- The other person clones that repo
- make changes on a new branch
- push the changes
- submit a Merge Request
- wait for approval
- At the same time review a collaborators Merge Request
- (Optionally) Learn about [protecting branches](https://docs.gitlab.com/ee/user/project/protected_branches.html) and try it out. 
- (Optionally) learn about [merge conflicts](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) and try it out in your collaboration. 

## Exercise: Working as an external contributor (in pairs):
Both of you should take the following actions:
- Remove each other as collaborator from your repository
- Create an issue on the repository that you want to contribute to as external collaborator
- Fork that repo
- Clone your forked repo to your computer
- Make some changes, use a somewhat real-world example so it makes sense to review it (but don't overdo it).
- Push it to your fork
- make a Merge Request from your fork to the main repository mentioning the issue
- Consider turning your Merge Request into a draft Merge Request.
- let your code be reviewed by tagging the repo owner using (@Username)
- At the same time review Merge Request using comments on individual lines. Try to act as if it was a real peer review as much as possible.
- Accept or reject the Merge Request
- (Optionally) learn about [merge conflicts](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) and try it out in your collaboration. 
## 🧠 Collaborative Notes
# Intro - Why version control?
Everybody has its own 'version' of version control. However, this sometimes can differ among people for the type of tech involved (e.g., one can use onedrive, or google drive), the complexity of the project (e.g., if there are multiple files/documents). Keeping tracks of all the changes thus becomes tricky, especially when there are more people involved in a project. One of the most widespread and standardised systems to simplify this task (i.e., version control) is git.

Git keeps track of changes in documents (e.g., additions, deletions) over time. Moreover, multiple people can work on the same document/file and merge their changes in a programmatic way.

To summarise the key concepts:

- version control is like an unlimited 'undo'
- version control also allows many people to work in parallel.

# Configure Git 
Open a terminal:

- **On Windows**: Click Start and search for "Command Prompt"
- **On Mac**: Click the Launchpad icon in the Dock, type Terminal in the search field, then click Terminal

Set-up git. First of all, we configure our username by typing the following line in the terminal:

```
git config -- global user.name "mybeautifulname"
```

We now configure our email by typing:

```
git config --global user.email "myemail@gmail.com"
```

Note that git keeps track also of the idriosyncracies of the OS system. In order to not create any conflicts due to this aspect, it's important to set-up git according to the OS system used.

For **Windows**:

```
git config --global core.autocrlf false
```

For **Mac**:

```
git config --global core.autocrlf input
```

>> **Question**: can any of the settings above can be changed at some point? 
>> Yes. Any setting can be changed at any point in time. However we need to be careful to not associate to our account multiple `aliases` (i.e., identities). Aliases are useful to keep track about who has made which changes. A good rule of thumb is to always google any setting that you wish to change beforehand, in order to be aware of all the changes.

Configure the editor. You can configure the default text editor that will be used when Git needs you to type in a message. If not configured, Git uses your system’s default editor. This step allows you to associate a name entity to your git account. 
Type:
```
git config --global core.editor "nano -w"
```

To see what settings you currently have, type:
```
git config --list
```
To exit from the list-view, just press Q.

To see all the possible configurations, type:
```
git config -h
```

However, if you wish to change configurations, or to set-up extra configurations, it's best to google it first. 

# Create a git repository
We are going to cover now how does git store all info, and how to create a repository.

Let's create a new repository, we will be calling it planets.

Create a new folder. Type in the terminal:

```
cd ~/Desktop
```

This will direct us to the Desktop directory. To check that you are within the desktop directory:

```
pwd
```

At this point you can make a new folder:
```
mkdir planets
```

## Initialise a git repository 
A git repo is a place (e.g., a folder) where we store our work (e.g., documents, files in general). This corresponds to a repository online.

Type:
```
git init
```

This will prompt multiple hints (in green), followed by:

```
Initialized empty Git repository in ~/Desktop/planets/.git/
```

To inspect the (non-hidden) contents of the folder:
```
ls
```

This however shows only the non-hidden files. To see verything, also the hidden ones:

```
ls -a
```

This will show that there is something, i.e., the `.git` folder. Let's see what's inside:

```
ls -a .git
```

This will show what it is inside the folder. We don't have to care about the folder's content now, as this is mostly relataed to the configuration files -- for the moment it's important to be aware of this.

## Branches
Branches are versions of the same repository. Branches allow you to develop features, fix bugs, or safely experiment with new ideas in a contained area of your repository, without necessarily affecting someone else's work.

Let's switch to a branch in the main planet repository:

```
git checkout -b main
```

This will prompt the message `Switched to a new branch 'main'` which means that we have successfully diverged into our branch, called `main`.

To display the state of the working directory and the staging area:

```
git status
```

>> **Question**: is git really made for storing documents or storing software?
>> Software it is written in a code editor, and usually are small files (few MB). A good rule of thumb is to store software separate from your data (e.g., on [zotero](https://www.zotero.org/)). The reason is that Github is not really made to store big large data files. Another solution is to build a [docker](https://www.docker.com/) image whereby you can store your data, so that you can load from your code without storing it on github repo. Docker is an open source containerization platform.
>> **Question**: How about storing theses? or papers?
>> Git prompts you a warning for files `> 5GB`. It doesn't matter the type.

>> **Question**: If I transfer to another university, and therefore I will have a different user account, will I lose access to the repository?
>> You might. In these cases, it's best to make youre repository public, so that you can `fork` it from any other account. Ithowever also depends on the type of `licence` under which your work is registered. If you wish to have personalised info for your project, email: data@wur.nl

>> **Question**: When you create branches, and you wish to commit to both your branch and your main, is it possible to submit to both places?
>> Yes, you can create multiple remotes (i.e., multiple copies in the cloud) and push it at the same time. You can google it as `git set up multiple remotes`.

## Tracking changes
Go to the planet folder (if you haven't done that before), by typing:

```
cd ~Desktop/planets
```

We open our editor and create a new file called `mars.txt` by typing:

```
nano mars.txt
```
This will open a code editor, and an empty `txt` file. Let's make any changes. Write: `Cold and dry, but everything is my favourite colour`. To exit: ctrl+X. Confirm the changes by typing: `Y` as it stands for yes.

Let's check that our file is really there:

```
ls
```

We can see now that we got the `mars.txt` file. A quick way to see what's in the `mars.txt` file, is to type:

```
cat mars.txt
```

This will prompt git to highlight the changes under `untracked files`. The changes are highlighted in `red`. It also suggests to use `git add` to track the new file.

Let's follow the suggestions:
```
git add mars.txt
```

And let's re-check our status with `git status`. This will prompt git to highlight our changes in green. We now save the changes by doing a `commit` (i.e., set of changes that we label for future reference) the changes, by adding a personalised message with `-m`:

```
git commit -m "Start notes onb Mars as a base"
```

>> **Q**: why do we need to have the `git add` step? can we commit multiple things?
>> Git `add` allows you to keep track of the changes, git `commit` however it saves them permanently.
 
>> **Q**: can we ignore particular files? 
>> Yes, you can do that. You can work into git history, and how to undo things. The reason why you need to have `atomic` commitments is that this way if your wish to change anything in the future, you can trace back exactly which commit was key. 


### Commit messages
What is a good commit message? Tip: think to a message as a way to fill in the following phrase: `If X applied, this commit will...`. As a rule of thumb, write something that you may be able to understand in a year time. Make it **short**, **descriptive**, and **imperative**.

Let's inspect our changes so far, we type:

```
git log
```

This will prompt git to show who did the commit, and when. It also shows the `hash` number that is a unique identifier of a commit. To exit the log, press Q.

Let's open our editor again:

```
nano mars.txt
```

We make another change. We add another line. We confirm again, and we check if the changes have been saved by typing:

```
cat mars.txt
```
It says now that there are again `changes not staged for commit`, and we have two options:

- git add, keep track of the latest changes
- git restore, discard the latest changes

To highlight the changes:

```
git diff
```

This will shows you new changes in green with a `+` symbol. We now commit the new changes, with a message:

```
git commit -m "Add concerns about effects of Mar moons on Wolfman"
```

However, Git says `no changes added to commit`. We have forgot indeed to add the file with `git add mars.txt`. We can now repeat the previous step `git commit -m` with our message. 

## Staging area

The overall idea is that you start making changes to some files stored in our git folder. When we add changes, we add them to the staging area while git commit adds them to your repository. 

We now make new changes. We add a new line in which we write anything, and we highlight the new changes by tipyng:

```
git diff
```
To add this change to the staging area, we do:

```
git add mars.txt
```

Note that git diff shows only changes that are NOT in our staging area. To see those that are in the staging area instead we type:

```
git diff --staged
```

We're ready to commit now:

```
git commit -m "Discuss concerns about mar's climate for mummy"
```

If we double-check now our status with `git status` it says that our repository is clean, there are no new changes or things that have not committed/staged yet.

To inspect our history:

```
git log
```

>> **Question**: what is the working tree?
>> It's your working directory, anything that is before your staging area.

**TIP**: If you encounter any issues with access (i.e., access denied because of X). Please check that you have a working VPN connected.
**TIP**: When you make changes these are saved locally on your laptop. This means that you can visualise them also locally (i.e., not necessarily via your terminal).


## Exploring History

0. tips for us: request to put all the exercises in the hackmd
1. "Bending time" How to look back in time
first git change into your folder, then change something

Make a change to mars.txt, add that change, and use git checkout to see if you can remove your change.
$ git diff [ID] mars.txt  # ID of most recent commit
  ``git diff HEAD mars.txt```
  



We can also go back further (one step)
```git diff HEAD~1 mars.txt```

We can also go back further (one step)
```git diff HEAD~1 mars.txt```

We can look at all of it (exactly what happened)

``` git show HEAD~X mars.txt```
We can also use git diff across  a hash number e.g.
``` git diff 82552454378567834685f897 mars.txt```
or
``` git diff 825524b mars.txt```
Note above we only used the first part of the hash , the 'lazy way'  we could have have used the whole hash number

What is we want to change the history. We have a modified file , so how can we roll it back ?
HEAD is the pointer to the last commit on the stack. If I want to go back to that I can use 
```git checkout HEAD mars.txt```
If I want to go back to another spefici place, I can find the hashes in the log
```git log```
then I can use that hash number i.e.
```git checkout 1aa681bec mars.txt```
Note the commit messages are a message to self also. Now if you want to go back to where you were before
```git checkout HEAD```
We can go backwards and forward in time for a certain file.
To recap on git workflow:
There is a first pitstop for a staging area. Once you are satisfied put it on the stack of commits.
The top commit is always called HEAD. You can browse the existing commits.

Now let's try adding a disaster. We will go back to a first commit

```git checkout 1aa681c0fc```
Now we did not specify a file. What happens? We go to a detached head state. What is this? We rolled back the whole repository. If we make changes now we create a new virtual branch. If we do more changes, it will continue on that branch, which is ephemeral. We can create a new branch which re-attahces the head. 
```git checkout -b "new branch"```
you also can roll back to the main branch
```git branch main```
Checkout: can switch branches, or checkout a commit. It may be better to use git switch. Git will tell you what to do (let Git help you).

Let's make some more changes, on git status, we see it tells us what we can do i.e. add or restore
Let's assume we added, but we don't want to. Run:
```git restore --staged```
Then we want to undo the unstaged changes
```git restore marx.txt```

Notice that Git tells you how to do these things.
Quiz: 'Deleted a line in mars.txt' How can I go back to the last commited version?

1. git checkout HEAD
2. git checkout HEAD mars.txt
3. git checkout HEAD~1 mar
4.  git checkout <ID of last commit> mars.txt

1. restores all files, erasing all changes, and detaches HEAD ⚠️
2.reverts only mars.txt by one commit
3.reverts mars.txt to an earlier version ⚠️
4. is equivalent to 2.
    
Quiz 2:
    I committed a file with an error! How can I revert a commit?
Find the commit ID where you want to revert to.
$ ???
Copy the first 7 characters of that ID, e.g. 825524b
$ git revert [commit ID]
Type commit message
Save and close editor

Tips: pager
    ```git log``` with setting in config or
    ```git log | less```
Quiz 3:
     What would happen if I do...
$ cd planets
$ echo "Venus is beautiful and full of love" > venus.txt
$ git add venus.txt
$ echo "Venus is too hot for a base" >> venus.txt
$ git commit -m "Comment on Venus as a base"
$ git checkout HEAD venus.txt
$ cat venus.txt
    
We commit what we have in the staging area, then we checkout the last commit ->
    we commited the previosly staged venus.txt
    revert local changes, and finally print out the last line
Change into directory 'planets'
Add "Venus is beatiful and full of love" to venus.txt
Add venus.txt to staging area / index
Append "Venus is too hot for a base" to venus.txt
Commit the _previously staged_ venus.txt
Revert local changes of venus.txt, and finally print
Venus is beautiful and full of love

Quiz 4/4
    Diff, What If... 🤔
$ git diff HEAD~100 mars.txt
    
Awnser you can't. "ambigous argument" because it did not exist
    
Exercise 1/2
git checkout can be used to restore a previous commit when unstaged changes have been made, but will it also work for changes that have been staged but not committed?


Exercise 2/2
Exploring history is an important part of Git. How can you find a commit ID from waaaaay back?

1. Find a previous commit message
$ git log mars.txt 
    Search the list
2. Find a previous change in file content with
$ git log --patch mars.txt 
    Search the list
        
Useful tip:
```git log --patch <file>```

Note in the real world you may change more than one line, and you will see all changes.
    
## Tracking Changes: Key Points
```git diff ``` displays differences between commits
```git checkout```  recovers old versions of files

## Ignoring Things
How can I tell Git to ignore files I don’t want to track?
Imagine we have files we don't want
A New Beginning
$ cd ..                 # exit the 'planets' directory
$ mkdir project         # create a new directory 'project'
$ cd project            # change into directory 'project'
$ git init              # create a new git repository
$ git checkout -b main  # switch to 'main' if necessary

We now have a new repository. Imagine we make a folder results i.e.
```mkdir results```

We create a few files
```touch a.dat b.dat c.dat results/a.out results/b.out```
We can display this on some computers with
```tree```
But you might not have the tree command

Then we can add these untracked files...
But what if we don't want to have some of these staged in our git history?
Now we can add a .gitignore file
This special file tells the git what to ignore, and * is usas a 'wildcard'
    ```$ nano .gitignore
    $ cat .gitignore
    *.dat
    results/```
    
Now to distribute and keeps we need to 

``` git add .gitignore```
```git commit -m "message"```
Now everyone else who gets repo will have this gitignore. So their results will be ignored as well

If we try to add something in the .gitignore- it will remind us that we can't. We can only do it if we force it ie. with -f flaf
We can check ignored files
```git status --ignore```

Quiz: Ignoring Nested Directories
Imagine having the following directory structure:

 results/data
 results/plots 
How can you ignore only one sub-directory?

Quiz awnser: 
    ```$ cat .gitignore 
    results/plots/```
Basically pay attention to the syntax inside your .gitignore file.Another option is to add
```directory/```
then all the files inside directory ignored.
We can also 

	file.txt              # the file "file.txt"
directory/            # the directory "directory" and content
*.log                 # all files ending with ".log"
error_?.log           # "error_1.log", "error_A.log", ...
error_[a-z].log       # "error_a.log", "error_b.log", ...
!error_important.log  # do _not_ ignore "error_important.log"
**/secret             # _all_ "secret" folders and content, everywhere
/home/ole/**/secret   # as above, but only within /home/ole/

The double star means anywhere in the file tree means anywhere in the file tree, and also works within 
paths. i.e. home/ole/**/secrets will disincldue anything in ole's home folder called secrets (anywhere on path no matter how deep)


	Quiz: Perfecting Ignoring 1/2
How to ignore all .dat files, except final.dat?

```*.dat           # ignore all data files```
```!final.dat       except final.data```


How to ignore everything in results/, except results/data?

```results/*       # ignore everything in results folder```
    ```!results/data/  # do not ignore results/data/ contents```

What's the shortest .gitignore to exclude all .dat files in result/data/position/gps? Do not ignore the info.txt.
results/data/position/gps/a.dat
results/data/position/gps/b.dat
results/data/position/gps/info.txt
results/plots

Awnser: 	results/data/position/gps/*.dat

You have many scattered .dat files. How can you ignore all of them?
results/a.dat
data/experiment_1/a.dat
data/experiment_2/b.dat
data/experiment_2/variation_1/d.dat
[and many more...]

Awnser: **/*.dat

Contradictions
What does the following .gitignore file achieve?

 *.dat
 !*.dat 
 
 Awnser: nothing
 
 Hands on exercise: 
 You generated many log files of the form log_01, log_02, ... You want to keep them, but not track them with Git.
Write one .gitignore to exclude them.
Test your "ignore pattern" by creating dummy files of the form log_01, log_02, ...

The pattern you want is log_*

But imagine later you found out log_1 was important?

```git add -f log_01```

You force it, but you will need to do this every time you update it.

Summary: .gitignore file tells git what to not share i.e. which files and folders not to

Note: There will be some materials skimmed, the slides should be there. 


## Remotes in GitLab
How do I share my changes with others on the web?

HEAD in the Cloud ☁️ (exercise to tbe done on student machines)
To really collaborate with others, we need a shared repository. Let's create one on gitlab.com.

Log in if you aren't already
Click the ➕ on the top right
Choose New project/repository
Choose Create blank project
Name your project "planets"
Pick a group or namespace, if necessary
Set the visibility to Public
Unset (!) Initialize repository with a README
Click Create project


Just Another Repository?
You effectively executed on the GitLab server:

$ mkdir planets 
$ cd planets
$ git init

There is nothing special about Gitlab, you can make your repos there. So...
The Holy Realms of Git - Extended
workspace  📂 Your filesystem
index  🕒 Staging area, Files wait patiently to be committed
local repository  🗂️ Contains branches, commits, history, etc.
remote repository  ☁️
Cloud or self-hostet Git{Hub,Lab} , Shared folder

So lets connect these different realms. 
```cd existing_repo```
```git remote rename origin ```
```git remote add origin <>```

	$ git remote add origin git@github.com:vlad/planets.git
 
Confirming  that it worked
$ git remote -v
origin   git@github.com:vlad/planets.git (fetch)
origin   git@github.com:vlad/planets.git (push)


Now making local repo available to outside world

```$ git push -u origin main  # -u means "set upstream"
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 8 threads.
Compressing objects: 100% (11/11), done.
Writing objects: 100% (16/16), 1.45 KiB | 372.00 KiB/s, done.
Total 16 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/vlad/planets.git
 * [new branch]      main -> main
```


Now explore repository. Windows can have a password manager. We can explore the Gitlab interface U/I , and there explore the repository. But we can get the same information at the terminal (we did this before i.e. git log etc. )

Explore the GitLab UI 1/2
Browse the planets repository on GitLab
Click on ⦵ X Commits under the header
Click on the ellipsis · · · next to a commit
Click on a commit itself
Click on Browse files

How can you get the same information from the terminal?

git log
git diff ID1..ID2
git checkout ID  # don't forget to put back the repo in a good state!
Note the relative timestamp in the commit list. 
To get absolute hover over the timestamp.

Explore the GitLab UI 2/2
How can you ...

download a file from GitLab? 
upload a file to GitLab?
create a file on GitLab?
edit a file from GitLab?
- All are possible from the U/I from the Gitlab

Quiz:What is the difference between commit and push?
Awnser to quiz: A commit writes changes to local repository only, but the push goes to the remote i.e. we push the changes into the cloud.

Remotes: Key Points
A local Git repository can be connected to one or more remote repositories
Use the SSH protocol to connect to remote repositories
git push copies changes from a local repository to a remote repository
git pull copies changes from a remote repository to a local repository

## Collaborating!
We want to collaborate with peers.
This could include others we might not know.
Example using the public gitlab.
Sven creates a new project in gitlab U/I
He looks to add Ole, but INvite members- makes him a maintainer without expiration. Sven creates an issue <New issue button>. He assigns it to Ole. Ole will get a notification, and he can start working on it. It will also appear in top right (issues assigned to him). Ole clones off the repo, 
    ```git clone git@gitlab.com/svenvanderberg/wdcc-git```

    Then Ole adds a .py file, with a function inside. He then adds and commits. He had been on the main branch...bad practice. We should in general, switch off to his own branch (after rolling back the staging). He then tries to push it (it is not on the remote yet)
    ```git push set upstream origin <blabla>```
    
He then creates a merge request. 
    
Note on naming branches: convention is yourusername/what-your-branch-does. This is so keeping track of branches is easy.
    
Specifying what to merge to what can be done in the U/I. Here we want to merge onto main. Sven reviews the code via the U/I. Pipelines can automatically check certain things. 
Sven demos a peer review. He can add a suggestion. Ole can immediately apply. Note @olemussman is a gitlab handle, and will send Ole a notification. (review commit). Ole can just apply suggestion through U/I. Then eventually he can merge it. Note the tied issue gets closed. To sync the local main, you need to pull what you just did on the main. 

    
Note: there is a second way of collaborating. Create a fork. 

    

    

    




Make a change to mars.txt, add that change, and use git checkout to see if you can remove your change.
$ git diff [ID] mars.txt  # ID of most recent commit

if mars.txt is the file we wanted to roll back. 

## :question: Questions
### What Questions do you have?
Q: How do I configure `git log` to print everything to my screen?
A: `git config --global core.pager cat`

Q: How do I configure `git log` to enter a pager (i.e. another dimension)
A: `git config --global core.pager less`

Q: Using get checkout out (nothing afterwards i.e. not HEAD)
A: It basically does nothing

Q: Is it possible to just remove a commit?
A: Yes, but not recommended, because other people will problems, just don't get rid of it unless you are the only one working on it...or you accidentally commit a password. There are very few reasons to change a git history. If you made a commit you don't like, still leave it in the history. And don't commit passwords or private ssh keys.

Q: How do I set up multiple remotes (for example use both Github and Gitlab to track a repository)?
A: Follow instructions [here](https://jigarius.com/blog/multiple-git-remote-repositories)

Q: If we remove something how does it know "which ones" know the relative path?
A: It's relative to where you are in teh structure

Q: Can I remove everything
A: rm *

Q: You said you can only commit to local, but you can also commit to gitlab?
A: it's perspective, to the Gitlab it can be a local repo

Q: what if I have both a github and gitlab, do I need two different ssh keys
A: Not neccesarily, but if it's super senstive, there is more risk in using one single key

Q: Why do we learn about git in the terminal and not with a graphical user interface (GUI) such as Rstudio, gitkraken or visual studio code?
A: Several reasons: 1) It forces you to really fully understand git 2) Not everyone uses the same GUI, but git works the same on the terminal for everyone 3) It works faster than a GUI 4) If you made a mess, you can often not solve it using a GUI and you need a terminal.
    
Q: why gitlab, not github?
A: We taught Gitlab in this workshop, because most people at WUR use this. But Gitlab and Github are very similar. They have a slightly different look and feel and some people prefer one over the other. But what you can do with it is 99% the same.
    
    
## 📚 Resources
* [escience center](https://www.esciencenter.nl)
* [digital skills workshops](https://esciencecenter-digital-skills.github.io/)
* [Editor options](https://git-scm.com/book/en/v2/Appendix-C:-Git-Commands-Setup-and-Config#ch_core_editor)
* [git config documentation](https://git-scm.com/docs/git-config)
* [docker image](https://www.docker.com/)
* [Great video about using Docker in research](https://www.youtube.com/watch?v=HelrQnm3v4g)
* [Dat Ecosystem](https://dat-ecosystem.org/)
* [Open-source Version Control System for Machine Learning Projects](https://dvc.org/)
* [4TU Reserach Data](https://data.4tu.nl/info/en/)
* [zotero](https://www.zotero.org/)
* [course on git @datacamp](https://app.datacamp.com/learn/courses/introduction-to-git)
* [happygitwithr](https://happygitwithr.com/)
* How do I write books (PhD thesis!) or manuscripts and then easily keep track of my progress using git
    - [quarto, the successor to RMarkdown, connects with git](https://quarto.org/)
    - [jupyter book](https://jupyterbook.org/)
    - [latex, has a steep-learning curve](https://www.latex-project.org/)
    
## Post-workshop survey
https://www.surveymonkey.com/r/TY2LHR2
