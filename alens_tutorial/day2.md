# Sciware

## Intro to GitHub

https://sciware.flatironinstitute.org/21_IntroGithub

https://github.com/flatironinstitute/learn-sciware-dev/tree/master/21_IntroGithub


## Rules of Engagement

### Goal:

Activities where participants all actively work to foster an environment which encourages participation across experience levels, coding language fluency, *technology choices*\*, and scientific disciplines.

<small>\*though sometimes we try to expand your options</small>


## Rules of Engagement

- Avoid discussions between a few people on a narrow topic
- Provide time for people who haven't spoken to speak/ask questions
- Provide time for experts to share wisdom and discuss
- Work together to make discussions accessible to novices

<small>
(These will always be a work in progress and will be updated, clarified, or expanded as needed.)
</small>


## Zoom Specific

- Dedicated Zoom moderator to field questions.
- Please stay muted if not speaking. (Host may mute you.)
- We are recording. Link will be posted on #sciware Slack.


## Future Sessions

- June 29: Showcase of code editors, development environments (show & tell)
- July 21 (preliminary): Shells, environments, command-lines


## Today's Agenda

- What is Git and GitHub? 
- Setting up git and GitHub on your computer
- Getting code off of GitHub
- Putting code onto GitHub



# Intro to Git and GitHub


## Version control

<div style="display: flex;">
<img src="http://www.phdcomics.com/comics/archive/phd101212s.gif" style="height: 16em; float: left;">
<ul>
<li>keeps track of history of one or more files</li>
<li>helps with backup and collaboration</li>
<li>makes it easier to combine changes to the same file</li>
</ul>
</div>


<a href="https://git-scm.com/"><img src="https://git-scm.com/images/logos/downloads/Git-Logo-Black.png" style="height: 4em; border: none; box-shadow: none;"></a>

*an open-source, distributed, command-line, version-control tool*

* released in 2005 by Linus Torvalds for developing Linux, as an alternative to older tools (CVS, svn)
* now the dominant tool for academic and industry software development
* **distributed**: no central server, every repo is fully functional, independent, and can "sync" with any other


## GitHub

* A central website for storing and sharing git repositories
* Started in 2008 as a freemium service, now owned by Microsoft
* Provides repository management, permissions, collaboration tools, CI, etc.



# Setting up GitHub on your Computer


## Make sure `git` is installed
<pre  style="font-size:1em;"> <code data-trim data-noescape>&gt; git version
git version 2.30.1
</code></pre>

<p class="align-left">If this returns an error, please raise your hand and put a red flag on your laptop.
</p>  


## Setting your name in Git 

**See what name is currently set**
<pre style="font-size:1em;"> <code data-trim data-noescape>&gt; git config --global user.name
</code></pre>

<div class="spacer"></div>

**Set your name**
<pre  style="font-size:1em;"> <code data-trim data-noescape>&gt; git config --global user.name "Mona Lisa"
</code></pre>


## Setting your email address

### See what email address is currently set
<pre  style="font-size:1em;"> <code data-trim data-noescape>&gt; git config --global user.email
</code></pre>

### Set an email address
<pre  style="font-size:0.9em;"> <code data-trim data-noescape>&gt; git config --global user.email "your_email@example.com"
</code></pre>
(Ideally set to the same email address you used for GitHub.)



## We Need Something Different

- When we want to make changes _separately_ from a main project
- We want to take an existing project in a _new_ direction
- Sometimes we want to make and track changes to repositories we don't have permissions to push to


## Forking to the Rescue

<img width=80% src="./assets/Learn-Git-Graphics/Forking%20a%20Repo.png">


## Forking Workflow

1. Fork and clone the project
2. Add the code and push to your fork
3. Merge code into the main project
4. Keep your fork up to date



## Step 1: Fork and Clone

<img width=80% src="./assets/Learn-Git-Graphics/Clone%20the%20Fork.png">


## Step 1: Fork and Clone

<div>
    First we need to fork the repo
    <img src="./assets/where_is_the_fork_button.png">
</div>
<style>
    pre {
    overflow-x: hidden;
    }
</style>

<div class="fragment">
    Next, we clone <em>our</em> fork of the repo:
    <pre  style="font-size:0.75em;">
        <code data-trim data-noescape class="language-zsh">
        ➜ git clone git@github.com:your_user_name/sciware21-git-intro.git
        </code>
    </pre>
</div>


## Step 1: Add an Upstream

 If you already have a copy of this repo from yesterday's workshop, that's ok, keep it!
<pre  style="font-size:0.75em;">
    <code data-trim data-noescape class="language-zsh" data-line-numbers="1,4,5,6">
    ➜ git remote -v
    origin  git@github.com:flatironinstitute/sciware21-git-intro.git (fetch)
    origin  git@github.com:flatironinstitute/sciware21-git-intro.git (push)
    ➜ git remote rename origin upstream
    ➜ git remote add origin git@github.com:jamesETsmith/sciware21-git-intro.git
    ➜ git remote -v
    origin  git@github.com:jamesETsmith/sciware21-git-intro.git (fetch)
    origin  git@github.com:jamesETsmith/sciware21-git-intro.git (push)
    upstream  git@github.com:flatironinstitute/sciware21-git-intro.git (fetch)
    upstream  git@github.com:flatironinstitute/sciware21-git-intro.git (push)
    </code>
</pre>



## Step 2a: Add Your Code

Add a file in `student_info` called `firstName_lastName.csv` with the following info:

- Your full name
- Your center
- Your research focus
- A fun fact


## Step 2a: Add Your Code

Mine looks like this:

<pre  style="font-size:0.75em;">
    <code data-trim data-noescape class="language-plaintext">
Name,Center,Research Focus, Fun Fact
James Smith, CCQ, Quantum Chemistry, My initials are JETS
    </code>
</pre>


## Step 2b: Push to Your Fork

<img width=80% src="./assets/Learn-Git-Graphics/Push%20to%20the%20Fork.png">


## Step 2b: Push to Your Fork

- Run `git add` on your file
- Commit it
- Push to your fork

Mine looks like this:

<pre  style="font-size:0.75em;">
    <code data-trim data-noescape class="language-zsh">
➜ git status
...
➜ git add student_info/james_smith.csv
➜ git commit -m "Adding info for James Smith"
...
➜ git push origin main
    </code>
</pre>



## Step 3: Open a Pull Request
<img width=80% src="./assets/Learn-Git-Graphics/Open%20a%20Pull%20Request%20for%20the%20Fork.png">


## Step 3: Open a Pull Request

- Using your browser, navigate to your forked repository
- It should look something like this:

<img src="./assets/pull_request_button1.png">

- Click on the `Contribute` button


## Step 3: Open a Pull Request

<img src="./assets/pull_request_button2.png">

- Click on the `Open pull request` button


## Step 3: Open a Pull Request

<img src="./assets/pull_request_form.png">


## Step 3: Open a Pull Request

Things to think about when making pull requests (PR):

<ul>
<li>Many projects have PR templates with information you need to fill out, <b><em>use them</em></b>!</li>
<li class="fragment">Include <b><em>why</em></b> you're making the PR, what steps you took, and how it addresses a current problem.</li>
<li class="fragment">Bug reports should <b><em>always</em></b> include a minimum working example.</li>
<li class="fragment">PRs (and Issues) are a valuable <b><em>public</em></b> record, just like StackOverflow.</li>
</ul>



## Step 4: Pull Other's Changes
<img width=80% src="./assets/Learn-Git-Graphics/Pull%20from%20upstream.png">


## Step 4: Pull Other's Changes

If the original repo from `flatironinstitute` isn't your upstream, set it now and then pull from it.

<pre  style="font-size:0.75em;">
    <code data-trim data-noescape class="language-zsh" data-line-numbers="1,4,5,10">
    ➜ git remote -v
    origin  git@github.com:flatironinstitute/sciware21-git-intro.git (fetch)
    origin  git@github.com:flatironinstitute/sciware21-git-intro.git (push)
    ➜ git remote rename origin upstream
    ➜ git remote add origin git@github.com:jamesETsmith/sciware21-git-intro.git
    ➜ git remote -v
    origin  git@github.com:jamesETsmith/sciware21-git-intro.git (fetch)
    origin  git@github.com:jamesETsmith/sciware21-git-intro.git (push)
    upstream  git@github.com:flatironinstitute/sciware21-git-intro.git (fetch)
    upstream  git@github.com:flatironinstitute/sciware21-git-intro.git (push)
    ➜ git pull upstream main
    </code>
</pre>


# Survey

## http://bit.ly/sciware-github2-2021

## Reviewing a Pull Request

As other students make PRs, go to the pull requests tab on GitHub.

![](./assets/pull_request_rev.png)


<<<<<<< HEAD
## Reviewing a Pull Request

Choose another student's PR and click on it.

![](./assets/pull_request_rev2.png)
=======

## Reviewing a Pull Request

As other students make PRs, go to the pull requests tab on GitHub.

![](./assets/pull_request_rev.png)
>>>>>>> 03e0cfdfb5860b54f3b80137b92244fe08f97673


## Reviewing a Pull Request

<<<<<<< HEAD
Click on the commit to see the diff of their changes and hover over a line until you see the `+` sybmol.

![](./assets/pull_request_rev3.png)



## PR Case Study

Here's an example of a PR _without_ a helpful description:

![](./assets/pr_case_study_bad.png)


## PR Case Study

Here's an example of a [PR](https://github.com/scikit-learn/scikit-learn/pull/20251) _with_ a helpful description:

<img height=70% width=60% src="./assets/pr_case_study_good.png">



=======
Choose another student's PR and click on it.

![](./assets/pull_request_rev2.png)


## Reviewing a Pull Request

Click on the commit to see the diff of their changes and hover over a line until you see the `+` sybmol.

![](./assets/pull_request_rev3.png)



## PR Case Study

Here's an example of a PR _without_ a helpful description:

![](./assets/pr_case_study_bad.png)


## PR Case Study

Here's an example of a [PR](https://github.com/scikit-learn/scikit-learn/pull/20251) _with_ a helpful description:

<img height=70% width=60% src="./assets/pr_case_study_good.png">



>>>>>>> 03e0cfdfb5860b54f3b80137b92244fe08f97673
## Extra Resources

Check out and bookmark these tutorials for more information about git and the forking workflow:

- [Bitbucket: Making a Pull Request](https://www.atlassian.com/git/tutorials/making-a-pull-request)
- [CodeRefinery: Distributed version control and forking workflow](https://coderefinery.github.io/git-collaborative/03-distributed/)



# Survey

## http://bit.ly/sciware-github2-2021
