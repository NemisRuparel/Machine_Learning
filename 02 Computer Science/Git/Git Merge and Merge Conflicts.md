# Git Merge and Merge Conflicts

## Git Merge

**Git merge** is a command used to combine changes from one branch into another branch.

It is commonly used when a feature is completed and needs to be integrated into the `main` branch.

### Example

Suppose a repository contains two branches:

```
main:           A---B---C
                         \
feature-login:             D---E
```

To merge `feature-login` into `main`:

```
# Switch to the destination branch
git switch main

# Merge the feature branch
git merge feature-login
```

After merging, both branches' changes are integrated into `main`.

## Types of Git Merge

### 1. Fast-Forward Merge

A **fast-forward merge** happens when the destination branch has no new commits since the feature branch was created.

```
Before:

main:       A---B
                 \
feature:          C---D

After:

main:       A---B---C---D
```

Git simply moves the destination branch pointer forward without creating a merge commit.

```
git switch main
git merge feature
```

### 2. Three-Way Merge

A **three-way merge** happens when both branches have new commits after they diverge.

Git uses three versions to combine changes:

- The common ancestor commit.
    
- The latest commit on the current branch.
    
- The latest commit on the branch being merged.
    

```
Before:

        C---D  main
       /
A---B
       \
        E---F  feature

After:

        C---D
       /     \
A---B         M  main
       \     /
        E---F
             feature
```

Here, `M` represents the merge commit.

To create a merge commit even when a fast-forward is possible:

```
git merge --no-ff feature
```

## Merge Conflicts

A **merge conflict** occurs when Git cannot automatically combine changes from different branches.

Conflicts commonly occur when two branches modify the same lines of a file in incompatible ways.

Git pauses the merge and asks the developer to resolve the conflicting content.

### Example

Suppose `main` contains:

```
message = "Hello"
```

The `feature` branch changes it to:

```
message = "Hello, Developer"
```

Meanwhile, `main` changes the same line to:

```
message = "Hello, Git"
```

When the feature branch is merged into `main`, Git may report a conflict because both branches changed the same line differently.

### Conflict Markers

Git displays conflicting content using special markers.

```
<<<<<<< HEAD
message = "Hello, Git"
=======
message = "Hello, Developer"
>>>>>>> feature
```

- `<<<<<<< HEAD` marks the beginning of the current branch's version.
    
- `=======` separates the two versions.
    
- `>>>>>>> feature` marks the end of the incoming branch's version.
    

These markers are temporary conflict indicators, not valid Python syntax.

## Resolving Merge Conflicts

### Step 1: Check the conflict

```
git status
```

Git identifies the files that need conflict resolution.

### Step 2: Open the conflicting file

Choose the content you want to keep, or combine both versions.

For example:

```
message = "Hello, Git and Developer"
```

Remove all conflict markers and ensure the final file contains valid code.

### Step 3: Stage the resolved file

```
git add filename.py
```

Staging the file tells Git that the conflict has been resolved in that file.

### Step 4: Complete the merge

```
git commit
```

For a normal merge that stopped due to conflicts, this completes the merge by creating the merge commit.

Git usually prepares a default merge message automatically.

### Complete Workflow

```
# Switch to the destination branch
git switch main

# Merge the feature branch
git merge feature

# Check for conflicts
git status

# Resolve the conflict in the file, then stage it
git add filename.py

# Complete the merge
git commit
```

If several files have conflicts, resolve and stage each one before completing the merge.

## Aborting a Merge

If you want to cancel a merge that is still in progress:

```
git merge --abort
```

This attempts to restore the pre-merge state. It may not fully restore changes in unusual situations, particularly when the working tree had conflicting or uncommitted changes before the merge began.

## Useful Merge Commands

|Command|Description|
|---|---|
|`git merge branch-name`|Merges a branch into the current branch|
|`git merge --no-ff branch-name`|Creates a merge commit instead of fast-forwarding|
|`git merge --abort`|Attempts to cancel an in-progress merge|
|`git merge --continue`|Continues a merge after conflicts have been resolved and staged|
|`git status`|Shows merge status and unresolved files|
|`git diff`|Displays changes, including unresolved conflicts|
|`git diff --check`|Checks for whitespace errors and conflict markers|

## Git Merge vs Git Rebase

Both commands integrate changes from different lines of development, but they work differently.

|Feature|Merge|Rebase|
|---|---|---|
|Operation|Integrates branch histories|Replays commits onto a new base|
|Existing commits|Preserves existing commit identities|Replayed commits receive new identities|
|Merge commit|May create one|Does not create a merge commit as part of the rebase itself|
|History|Can preserve branching structure|Produces a more linear history|
|Conflict resolution|May require resolving conflicts|May require resolving conflicts for individual commits|

## Important Points

- Merge integrates changes into the current branch.
    
- A fast-forward merge moves a branch pointer without creating a merge commit.
    
- A three-way merge combines diverged histories.
    
- Merge conflicts require manual or tool-assisted resolution.
    
- Always remove conflict markers before completing a merge.
    
- Use `git merge --abort` if you need to cancel an in-progress merge.
    
- Avoid committing unresolved conflict markers into the final source code.
    

## Summary

**Git merge** combines changes from different branches. When Git cannot determine how to combine changes automatically, it reports a **merge conflict**. Resolve the conflicting content, stage the affected files, and complete the merge.