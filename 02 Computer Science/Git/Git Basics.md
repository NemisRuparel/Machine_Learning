# Git Basics

## 1. What Is Git?

Git is a free, open-source, distributed version control system (DVCS) used to track changes in files over time.

It allows developers to maintain a history of their work, compare changes, restore earlier versions, and collaborate on software projects.

### Why Use Git?

- Track changes to source code.
    
- Maintain a history of project development.
    
- Identify when and why changes were made.
    
- Restore previous versions of files.
    
- Work on projects without requiring a constant internet connection.
    
- Support collaboration between developers.
    

## 2. What Is Version Control?

Version control is a system that records changes to files so that earlier versions can be inspected or recovered.

Without version control, developers might create files such as:

```
project/
├── app.py
├── app-final.py
├── app-final-v2.py
└── app-final-corrected.py
```

Git provides a structured history of changes instead of requiring developers to maintain multiple manual copies.

## 3. Types of Version Control Systems

### Local Version Control

Tracks file changes on a single computer.

### Centralized Version Control

Uses a central server to store project history and coordinate collaboration.

### Distributed Version Control

Each clone contains a repository with its own history. Developers can work locally and exchange changes with remote repositories.

Git is a distributed version control system.

## 4. Essential Git Terminology

|Term|Meaning|
|---|---|
|Repository (repo)|A project directory managed by Git|
|Working directory|Files and changes currently present in your project|
|Staging area|The area containing changes selected for the next commit|
|Commit|A recorded snapshot of staged changes|
|Commit history|The sequence of recorded commits|
|`.git` directory|Stores repository metadata and Git's local database|
|Remote|A reference to another repository, often hosted online|
|HEAD|A reference indicating the current checkout position|
|Hash|An identifier used to identify Git objects and commits|
|Tracked file|A file Git already knows about|

## 5. Installing Git

On Ubuntu or Debian-based Linux distributions:

```
sudo apt update
sudo apt install git
```

Verify the installation:

```
git --version
```

Example output:

```
git version 2.x.x
```

The exact version depends on your installed Git package.

## 6. Basic Git Configuration

Configure your commit identity:

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Verify the configuration:

```
git config --global user.name
git config --global user.email
```

The `--global` option applies the setting to repositories for your user account. A repository-specific configuration can override it.

The configured name and email are recorded in your commits. They do not, by themselves, authenticate you to GitHub.

## 7. Initializing a Repository

Create a project directory and initialize Git:

```
mkdir git-basics
cd git-basics
git init
```

Git creates a `.git` directory to store repository information.

Check the repository status:

```
git status
```

## 8. The Basic Git Workflow

The basic workflow has four main stages:

1. Modify files in the working directory.
    
2. Select changes and place them in the staging area.
    
3. Commit the staged changes.
    
4. Inspect the repository history.
    

The three principal areas are:

- Working directory
    
- Staging area (index)
    
- Local Git repository
    

## 9. Essential Commands

|Command|Purpose|
|---|---|
|`git init`|Initialize a repository|
|`git clone URL`|Copy an existing repository|
|`git status`|Show the current state of files|
|`git add FILE`|Stage a file's changes|
|`git commit -m "MESSAGE"`|Record staged changes|
|`git log --oneline`|Display a compact commit history|
|`git diff`|Show unstaged changes|
|`git diff --staged`|Show staged changes|
|`git config`|Read or modify Git configuration|

## 10. Important Points

- Git and GitHub are different.
    
- Git can work entirely offline for local operations.
    
- A commit records the staged changes, not automatically every modified file.
    
- Git does not automatically track every file in a directory.
    
- A local commit is not automatically uploaded to GitHub.
    
- A repository's `.git` directory contains important repository data and should not be deleted casually.
