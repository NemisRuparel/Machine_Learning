# Git vs GitHub vs GitLab

**Git**, **GitHub**, and **GitLab** are tools used in software development to manage code changes, store repositories, and collaborate with other developers.

- **Git** is a version control system used to track changes in files.
    
- **GitHub** is a platform used to host Git repositories and collaborate on projects.
    
- **GitLab** is a platform used to host Git repositories and manage software development workflows, including CI/CD.
    

## Git

**Git** is a free, open-source, distributed version control system created by Linus Torvalds in 2005.

It helps developers track changes in source code, maintain project history, and manage different versions of a project.

```
git init
```

The `git init` command initializes a Git repository in the current directory.

## GitHub

**GitHub** is a web-based platform that hosts Git repositories and provides tools for collaboration.

It allows developers to store code online, share projects, review changes, and manage development tasks.

```
git remote add origin https://github.com/username/repository.git
git push -u origin main
```

The `git remote add` command connects a local repository to a remote GitHub repository, while `git push` uploads local commits to the remote repository.

## GitLab

**GitLab** is a Git-based platform that provides repository hosting, collaboration, continuous integration and delivery (CI/CD), and software development tools.

It allows developers to manage code, review changes, automate testing, and deploy applications.

```
git remote add origin https://gitlab.com/username/repository.git
git push -u origin main
```

These commands connect a local repository to GitLab and push local commits to the remote repository.

## Difference Between Git, GitHub, and GitLab

|Feature|Git|GitHub|GitLab|
|---|---|---|---|
|Type|Version control system|Repository hosting platform|DevSecOps platform|
|Main purpose|Track code changes|Host and collaborate on code|Manage development workflows|
|Repository|Local repository|Remote repository hosting|Remote repository hosting|
|Branching|Supported|Supported|Supported|
|Code review|Through Git-based workflows and tools|Pull Requests|Merge Requests|
|Automation|Requires additional tools|GitHub Actions|GitLab CI/CD|
|Internet required|Not for most local operations|For remote platform access|For remote platform access|
|Website|[git-scm.com](https://git-scm.com/)|[github.com](https://github.com/)|[gitlab.com](https://gitlab.com/)|

## How They Work Together

Git, GitHub, and GitLab can be used together to manage a software project.

1. Write code on your computer.
    
2. Use Git to track changes and create commits.
    
3. Push the commits to GitHub or GitLab.
    
4. Collaborate with other developers and review code changes.
    
5. Run automated tests and deploy the application when configured.
    

### Example

```
# Initialize a Git repository
git init

# Stage and commit changes
git add .
git commit -m "Initial commit"

# Connect to GitHub
git remote add origin https://github.com/username/repository.git

# Upload commits
git push -u origin main
```

## Summary

- **Git** tracks changes and manages versions of files.
    
- **GitHub** hosts Git repositories and provides collaboration features.
    
- **GitLab** hosts Git repositories and provides integrated development, CI/CD, and DevSecOps features.
    
- Git can be used without GitHub or GitLab.
    
- GitHub and GitLab both use Git for version control.