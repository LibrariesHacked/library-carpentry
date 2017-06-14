Teaching.  Git Foundations
==========================

Teaching
--------

| Term | Description |
| ---- | ----------- |
| Repository | A repository is the most basic element of GitHub. They're easiest to imagine as a project's folder. |
| Clone | A clone is a copy of a repository that lives on your computer instead of on a website's server somewhere |
| Branch | A branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or master branch allowing you to work freely without disrupting the "live" version. When you've made the changes you want to make, you can merge your branch back into the master branch to publish your changes. |
| Fork | A fork is a personal copy of another user's repository that lives on your account. Forks allow you to freely make changes to a project without affecting the original. Forks remain attached to the original, allowing you to submit a pull request to the original's author to update with your changes. You can also keep your fork up to date by pulling in updates from the original. |
| Commit | A commit, or "revision", is an individual change to a file (or set of files).  Commits usually contain a commit message which is a brief description of what changes were made. |
Merge Merging takes the changes from one branch (in the same repository or from a fork), and applies them into another.
| Pull | Pull refers to when you are fetching in changes and merging them. For instance, if someone has edited the remote file you're both working on, you'll want to pull in those changes to your local copy so that it's up to date. |
Pull Request Pull requests are proposed changes to a repository submitted by a user and accepted or rejected by a repository's collaborators.
| Push | Pushing refers to sending your committed changes to a remote repository, such as a repository hosted on GitHub. |
| Remote | This is the version of something that is hosted on a server, most likely GitHub. It can be connected to local clones so that changes can be synced |
| Diff | A diff is the difference in changes between two commits, or saved changes. The diff will visually describe what was added or removed from a file since its last commit. |
| Blame | The last modification to each line of a file, which generally displays the revision, author and time. This is helpful, for example, in tracking down when a feature was added, or which commit led to a particular bug. |

What is Git and GitHub?
-----------------------

We often hear the terms Git and GitHub used interchangeably but they are slightly different things.

**Git** is one of the most widely used version control systems in the world. It is a free, open source tool that can be downloaded to your local machine and used for logging all changes made to a group of designated computer files (referred to as a 'git repository' or 'repo' for short) over time. It can be used to control file versions locally by you alone on your computer, but is perhaps most powerful when employed to coordinate simultaneous work on a group of files shared among distributed groups of people.

Rather than emailing documents with tracked changes and some comments and renaming different versions of files (example.txt, exampleV2.txt, exampleV3.text) to differentiate them, we can use Git to store all the changes that have happened to a file over time. This makes it easy to get an overview of changes made by looking at a log of all changes (the 'Git history'). All earlier versions of each file still remain in their original form: they are not overwritten, should we ever wish to 'roll back' to them.

Git was originally developed to help software developers work collaboratively on software projects, but it can be and is used for managing revisions to any file type. Since documents like Word and PDF contain special formatting, Git unfortunately cannot show changes to these, though both file types can be stored in Git repositories.

**GitHub** is a cloud based implementation of Git.  Think of it perhaps like the different between music and iTunes, or spreadsheets and Google Sheets.  GitHub provides user management, online storing of repositories, and lots of associated tools and features for working with Git repositories.  We'll explore some of these now while looking at a few example repositories.

What can understanding Git do for Librarians?
---------------------------------------------

- Enables you to contribute, collaborate and support digital research projects
- True version control
- A place to discover and reuse ('fork') a huge amount of openly licensed digital projects and open source software
- A new and alternative means for publishing content online. Any GitHub repository can have its own project website, blog and wiki using GitHub Pages.  There is also GitBook: this website is automatically published from a repository of files [held on GitHub](https://github.com/LibrariesHacked/library-carpentry).

Uses in a Library Context
-------------------------

Scenario 1: Local librarian looking to start a crowdsourcing project

A local librarian is looking to put thousands of historical photographs of the area online so that the community can help identify the people and places they depict. She combs the web for examples of existing crowdsourcing projects, and even though they all appear unique to each institution, she notices quite a few seem to have almost the exact same functionality and structure. Rather than build a whole new version from scratch herself, she wishes there was a way to just copy the code of an existing one, and modify it to reflect her project. She notices the GitHub icon at the bottom of one of the projects she likes, but clicking on the link just brings her to a confusing directory of files and oddly labeled buttons such as “Fork”.

GitHub hosts open-licensed projects … and allows any user to fork any public project. By clicking the “fork” button, any GitHub user can almost instantaneously create their own version of an existing project. That “forked” project can be used as the basis for a new project, or can be used to work out new features that can be merged back into the original. (From: GitHub for Academics)

*Instructor: Browse a GitHub repository, paying attention to settings and options such as licensing and tagging.*


Source Materials
----------------

Library Carpentry [What is Git](http://data-lessons.github.io/library-git/01-what-is-git/)