# Git Objects

Git stores repository data using objects. These objects represent files, directories, commits, and tags in the repository.

Git uses four main types of objects:

- **Blob** → Stores file contents.
    
- **Tree** → Stores directory structure and references to blobs and other trees.
    
- **Commit** → Stores information about a snapshot of the repository.
    
- **Tag** → Stores information about a named reference, commonly used to mark releases.
    

## 1. Blob Object

A **blob (Binary Large Object)** stores the contents of a file in Git.

- Stores file contents without its filename.
    
- Can represent text files, images, and other file types.
    
- Does not store directory structure or file permissions.
    
- Identical contents generally produce the same blob object within the same Git object format.
    

### Example

```
echo "Hello Git" > hello.txt

git add hello.txt

git hash-object hello.txt
```

**Output:**

```
<blob-hash>
```

The hash identifies the blob object containing the file's contents.

To store the object in Git's object database, use:

```
git hash-object -w hello.txt
```

The `-w` option writes the object into the Git object database.

## 2. Tree Object

A **tree object** represents a directory in Git.

It stores entries for files and subdirectories, including their names, file modes, and object references.

- References blob objects for files.
    
- References other tree objects for subdirectories.
    
- Maintains the directory structure of a repository.
    
- Does not directly store file contents.
    

### Example

Consider the following directory structure:

```
project/
├── README.md
├── main.py
└── docs/
    └── notes.md
```

Git represents this structure using tree objects that reference blobs and other trees.

```
        Root Tree
        /       \
   README.md   main.py
     (Blob)     (Blob)
        |
     docs/
    (Tree)
       |
    notes.md
     (Blob)
```

To view a tree object associated with the latest commit:

```
git ls-tree HEAD
```

**Example output:**

```
100644 blob a1b2c3...    README.md
100644 blob d4e5f6...    main.py
040000 tree g7h8i9...    docs
```

The hashes above are illustrative.

## 3. Commit Object

A **commit object** represents a snapshot of the repository and records metadata about that snapshot.

It contains:

- A reference to the root tree object.
    
- The author's name and email.
    
- The committer's name and email.
    
- The commit message.
    
- The commit timestamp information.
    
- References to parent commit objects, except for the initial commit, which has no parent.
    

### Example

```
git commit -m "Add Python files"
```

To inspect the latest commit:

```
git cat-file -p HEAD
```

**Example output:**

```
tree a1b2c3...
parent d4e5f6...
author Nemis <nemis@example.com>  ...
committer Nemis <nemis@example.com> ...

Add Python files
```

The hashes and metadata are illustrative.

## 4. Tag Object

A **tag object** stores information about a tagged Git object, commonly a commit.

Annotated tags can contain:

- The target object's reference.
    
- The target object's type.
    
- The tag name.
    
- The tagger's information.
    
- A tag message.
    

Lightweight tags are different: they are simple references to an object and do not create a separate tag object.

### Example

```
git tag -a v1.0 -m "Version 1.0"
```

To inspect an annotated tag:

```
git cat-file -p v1.0
```

## How Git Objects Work Together

Git uses these objects to represent the history and structure of a repository.

```
Commit Object
     |
     v
  Root Tree
   /     \
 Blob    Tree
          |
         Blob
```

- The **commit** points to a root tree.
    
- The **tree** points to blobs and subtrees.
    
- The **blob** stores the actual file contents.
    
- The **tag** can identify a commit or another Git object.
    

When a file changes, Git creates a new blob if its contents differ. The affected tree objects and a new commit can then reference the updated content.

## Inspecting Git Objects

Git provides commands for examining objects directly.

|Command|Description|
|---|---|
|`git cat-file -t HASH`|Displays the object type|
|`git cat-file -p HASH`|Displays the object's contents in a readable form|
|`git hash-object FILE`|Calculates the Git object hash for a file|
|`git ls-tree HEAD`|Lists the entries in a tree|
|`git rev-parse HEAD`|Displays the current commit hash|

### Example

```
git cat-file -t HEAD
```

**Output:**

```
commit
```

```
git cat-file -t HEAD:README.md
```

**Output:**

```
blob
```

The second command identifies the object representing the contents of `README.md` in the current commit.

## Summary

| Object | Stores or represents                                           |
| ------ | -------------------------------------------------------------- |
| Blob   | File contents                                                  |
| Tree   | Directory structure and references to files and subdirectories |
| Commit | Repository snapshot, metadata, and parent references           |
| Tag    | Named reference; annotated tags also store tag metadata        |

Git objects form the foundation of Git's content-addressable storage system, allowing Git to identify repository data by hashes and preserve project history.