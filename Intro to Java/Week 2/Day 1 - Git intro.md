# **`Git Version Control`**

## **`What is Git?`**


Git is a distributed version control system that helps developers manage and track changes to source code during software development. It allows multiple developers to collaborate on a project, keep track of changes, and revert to previous versions when needed.


# **`Version Control`**
A version control system is a software that tracks changes to a file or set of files over time so that you can recall specific versions later. It also allows you to work together with other programmers or developers. The version control system is a collection of software tools that help a team to manage changes in a source code. It uses a special kind of database to keep track of every modification to the code.


# **`Git Benefits`**

- **Version Control:**
  - Git allows you to track changes in your code over time. This makes it easy to revert to a previous state of your project, compare changes, and understand the evolution of your codebase.

- **Collaboration:**
  - Git facilitates collaboration among developers. Multiple team members can work on different parts of a project simultaneously, and Git helps merge these changes seamlessly.

- **Branching and Merging:**
  - Branching enables developers to work on features or bug fixes in isolation without affecting the main codebase. Merging allows you to combine these changes back into the main branch.

- **Undo Changes:**
  - Git provides a safety net for mistakes. You can easily undo changes, revert to a previous commit, or discard modifications that are not yet committed.

- **History Tracking:**
  - Git maintains a detailed history of all changes made to the code. This includes who made the change, when it was made, and what was changed. This historical information is invaluable for debugging and understanding the project's development timeline.

- **Offline Working:**
  - Developers can work offline and commit changes locally. Once a connection is re-established, changes can be pushed to the remote repository. This is especially useful for developers who need to work in environments with limited or no internet access.

- **Efficient Collaboration:**
  - Git makes collaboration more efficient by allowing developers to work on their local copies of a repository. This reduces the need for constant communication with a central repository and speeds up development.

- **Distributed Development:**
  - Git is a distributed version control system, meaning that each developer has a complete copy of the repository. This decentralization makes it resilient and ensures that multiple copies of the project exist, reducing the risk of data loss.

- **Open Source Ecosystem:**
  - Git has a vast and active open-source community. This results in a wide range of tools, extensions, and integrations that enhance its functionality and make it adaptable to various workflows.

- **Ease of Branching:**
  - Creating branches in Git is a lightweight and fast process. This encourages the use of branches for different features or bug fixes, promoting a more organized and manageable development workflow.


# Configuring Git

Now that Git is installed, let's configure our environment using the `git config` command.

Git supports a command called `git config` that allows you to get and set configuration variables controlling how Git looks and operates. It is used to set Git configuration values on a global or local project level.

## Setting Username and Email

Setting `user.name` and `user.email` is necessary as they appear in your commit messages.

### Setting Username

The username is used by Git for each commit.

```bash
$ git config --global user.name "Firstname Lastname"
```


### Setting Email

Git uses this email for each commit.

```bash
$ git config --global user.email "test@mydomain.com"

```
# Git Configuration Levels

The `git config` command can accept arguments to specify the configuration level. The following configuration levels are available:

- **Local:** Default level in Git. Writes to the local level if no configuration option is given. Stored in the `.git/config` directory.

- **Global:** User-specific configuration, applied to an individual operating system user. Stored in the user's home directory.

- **System:** Applied across an entire system, affecting all users and repositories. Stored in a `gitconfig` file off the system directory.

## Configuration Level Details

### Local

The local configuration is the default level in Git. When no configuration option is given, Git config writes to the local level. Local configuration values are stored in the `.git/config` directory as a file.

### Global

Global configuration is user-specific and applied to an individual operating system user. These values are stored in the user's home directory.

### System

System-level configuration is applied across an entire system, affecting all users and repositories. The system-level configuration file is stored in a `gitconfig` file off the system directory.

## Git Config Command Usage

To set configurations at different levels, you can use the `--local`, `--global`, and `--system` options with the `git config` command.

Example:

```bash
# Set a configuration value at the local level
$ git config --local user.name "Local User"

# Set a configuration value at the global level
$ git config --global user.name "Global User"

# Set a configuration value at the system level
$ git config --system user.name "System User"



