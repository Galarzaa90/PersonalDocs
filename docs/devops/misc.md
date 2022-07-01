# DevOps

## git configuration per directory
If you are handling multiple git repositories in the same machine, but you require separate credentials (e.g personal, work), you can define settings that are applied only to repositories in a subdirectory.

In `.gitconfig`, add the `[includeIf]` block as shown below:

```conf
[user]
    name = Galarzaa
    email = allan@personal.com

[includeIf "gitdir:~/Galarza/git/work/"]
  path = .gitconfig-work
```

Create a new file, with the same name as in the path specified above:

```conf
[user]
    email = allan@company.com
```

Now, whenever you create a commit in a repository inside the specified folder, your work email will be used (unless it has been overriden for the specific repository).
