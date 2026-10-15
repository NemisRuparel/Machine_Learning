# Git Branches

A **branch** in Git is a separate line of development that allows developers to work on features, bug fixes, or experiments without directly modifying another branch.

Git branches are lightweight references to commits. The default branch is commonly named `main`.

## Creating a Branch

The `git branch` command creates a new branch.

```
# Create a new branch
git branch feature-login

# List all local branches
git branch

# List local and remote-tracking branches
git branch -a
```

**Output:**

```
* main
  feature-login
```

The `*` indicates the currently checked-out branch.

## Switching Branches

The `git switch` command switches to an existing branch.

```
# Switch to an existing branch
git switch feature-login

# Create and switch to a new branch
git switch -c feature-dashboard
```

The older `git checkout` command can also switch branches, but `git switch` provides a more focused interface.

## Creating and Switching Branches

A branch can be created and checked out using a single command.

```
git switch -c feature-profile
```

This creates `feature-profile` and switches the working directory to it.

## Listing Branches

```
# List local branches
git branch

# List remote-tracking branches
git branch -r

# List all branches
git branch -a

# Display the current branch name
git branch --show-current
```

## Renaming a Branch

The `git branch -m` command renames a branch.

```
# Rename the current branch
git branch -m new-name

# Rename another local branch
git branch -m old-name new-name
```

## Deleting a Branch

After a branch is merged and no longer needed, it can be deleted.

```
# Delete a merged local branch
git branch -d feature-login

# Force-delete a local branch
git branch -D feature-login
```

- `-d` deletes a branch when Git considers it safe to delete.
    
- `-D` force-deletes the branch even if it contains unmerged changes.
    

Deleting a branch does not automatically delete the commits if they are still reachable through other references, although commits that become unreachable may eventually be garbage-collected.

## Merging Branches

The `git merge` command integrates changes from another branch into the current branch.

```
# Switch to the main branch
git switch main

# Merge the feature branch into main
git merge feature-login
```

The current branch is the destination of the merge. In this example, changes from `feature-login` are merged into `main`.

Git may perform a fast-forward merge, create a merge commit, or report conflicts that require manual resolution.

## Pushing a Branch to a Remote Repository

A newly created local branch can be published to GitHub, GitLab, or another Git remote.

```
# Push the branch and set its upstream
git push -u origin feature-login
```

The `-u` option sets the upstream tracking branch, allowing subsequent `git push` and `git pull` commands to use the configured upstream by default.

## Deleting a Remote Branch

```
git push origin --delete feature-login
```

This requests deletion of the `feature-login` branch from the remote named `origin`. It does not delete the corresponding local branch.

## Branch Workflow

A typical feature development workflow uses a separate branch for each feature.

```
main
 |
 |---- Create feature branch
              |
              v
        feature-login
              |
        Make code changes
              |
           Commit
              |
              v
        Merge into main
```

### Example

```
# Start from the main branch
git switch main

# Create a feature branch
git switch -c feature-login

# Stage and commit changes
git add .
git commit -m "Add login feature"

# Return to main
git switch main

# Merge the feature branch
git merge feature-login

# Delete the local feature branch
git branch -d feature-login
```

## Common Branch Naming Conventions

|Prefix|Purpose|Example|
|---|---|---|
|`feature/`|New functionality|`feature/user-login`|
|`bugfix/`|Bug fixes|`bugfix/navbar-error`|
|`hotfix/`|Urgent production fixes|`hotfix/payment-error`|
|`docs/`|Documentation changes|`docs/git-guide`|
|`refactor/`|Code restructuring|`refactor/auth-service`|

These naming conventions are optional and depend on the project's workflow.

## Important Points

- A branch is a lightweight reference to a commit.
    
- Creating a branch does not duplicate the entire repository.
    
- Each branch can have its own commit history.
    
- Commits made on one branch do not automatically appear on another branch.
    
- `git switch` changes the current branch.
    
- `git merge` integrates changes into the current branch.
    
- Local branches and remote-tracking branches are different.
    
- A branch can be published to a remote repository using `git push`.
    

## Summary

Git branches allow developers to develop features, fix bugs, and experiment independently. Changes can later be integrated using merging or other Git workflows without requiring all development to happen directly on the main branch.