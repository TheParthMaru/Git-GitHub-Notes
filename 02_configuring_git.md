# Configuring GIT

## Levels of settings

- System: All users.
- Global: All repositories of the current user.
- Local: The current repository.

## `git config`

**Setting username**

```
git config --global user.name "Parth Maru"
```

**Setting user email**

```
git config --global user.email "theparthmaru@gmail.com"
```

**Setting default editor**

```
git config --global core.editor "code --wait"
```

- `--wait` tells the terminal to wait until we close VS Code.

**Setting configurations with default editor**

```
git config --global -e
```

- Running this command will create or open a `.gitconfig` file.

**Handling EOL**

- **Windows**: "abc\r\n" where `\r` is carriage return and `\n` is line feed.
- **Linux/Mac**: "abc\n" where `\n` is line feed.
- The issue is that for a repository, if one user is on windows and the other is on linux/mac, and if windows user pushes to the repo, he will be adding the `CR` or `\r` flag to the repo.
- This is of no use to Linux/Mac users and hence git should remove the `CR`.
- Also when windows user pulls code from the repo, git should add the `CR`.
- To enable this behavior we should do the following:

```
// Windows Users
git config --global core.autocrlf true

// Linux/Mac Users
git config --global core.autocrlf input
```
