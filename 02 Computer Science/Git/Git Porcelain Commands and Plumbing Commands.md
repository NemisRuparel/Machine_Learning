# Git Porcelain Commands and Plumbing Commands

Git commands are commonly categorized into two types: **Porcelain commands** and **Plumbing commands**.

- **Porcelain commands** → High-level commands used for everyday Git operations.
    
- **Plumbing commands** → Low-level commands used to interact with Git's internal mechanisms.
    

## Porcelain Commands

**Porcelain commands** are user-friendly commands used for common version control operations, such as staging changes, creating commits, managing branches, and synchronizing repositories.

### Common Porcelain Commands

|Command|Description|
|---|---|
|`git init`|Initializes a repository|
|`git clone`|Clones a repository|
|`git status`|Displays the working tree status|
|`git add`|Stages changes|
|`git commit`|Records staged changes|
|`git log`|Displays commit history|
|`git diff`|Shows differences between changes|
|`git branch`|Manages branches|
|`git switch`|Switches branches|
|`git merge`|Merges branches|
|`git restore`|Restores files or staged content|
|`git push`|Pushes commits to a remote repository|
|`git pull`|Fetches and integrates remote changes|

### Example

```
git init
git add README.md
git commit -m "Add README"
git status
git log
```

These commands are commonly used during software development.

## Plumbing Commands

**Plumbing commands** are low-level commands that interact more directly with Git's internal object database, index, references, and repository data structures.

They are useful for scripting, automation, debugging, and understanding Git's internal operations.

### Common Plumbing Commands

|Command|Description|
|---|---|
|`git hash-object`|Computes an object hash and optionally stores the object|
|`git cat-file`|Inspects Git objects|
|`git ls-tree`|Lists entries in a tree object|
|`git ls-files`|Lists files tracked by Git or present in the index|
|`git update-index`|Updates the Git index|
|`git write-tree`|Creates a tree object from the index|
|`git commit-tree`|Creates a commit object from a tree|
|`git symbolic-ref`|Reads or updates symbolic references|
|`git update-ref`|Updates Git references|
|`git rev-parse`|Resolves revision and reference names|

### Example

```
# Create a blob object and display its hash
git hash-object -w README.md

# Inspect a Git object
git cat-file -p OBJECT_HASH

# Display entries in the current commit's tree
git ls-tree HEAD
```

Replace `OBJECT_HASH` with the actual hash returned by the first command.

## Difference Between Porcelain and Plumbing

|Feature|Porcelain|Plumbing|
|---|---|---|
|Level|High-level|Low-level|
|Purpose|Everyday Git operations|Internal operations and automation|
|Ease of use|Generally easier|Requires deeper Git knowledge|
|Common users|Developers|Advanced users and script authors|
|Examples|`git add`, `git commit`, `git status`|`git hash-object`, `git cat-file`, `git write-tree`|

## Summary

- **Porcelain commands** provide convenient interfaces for everyday Git tasks.
    
- **Plumbing commands** provide lower-level access to Git's internal functionality.
    
- Both operate on Git repositories and can be used together.
    
- The distinction is conventional; some commands combine high-level workflows with lower-level functionality.