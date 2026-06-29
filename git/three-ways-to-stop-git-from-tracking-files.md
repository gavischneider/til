# Three Ways to Stop Git from Tracking Files

Git provides several ways to ignore files depending on whether you want the rules to be repository specific (personal or shared) or for all repositories.

## Repository Specific: Shared Rules

**File**: `.gitignore`

This is the most familiar method. You create a `.gitignore` file in your repository's root directory to tell Git which files and directories to ignore when you make a commit. The file is committed to the repository and version-controlled with all the other files.

## Repository Specific: Personal Rules

**File**: `.git/info/exclude`

If you don't want to create a `.gitignore` file to share with others, you can create rules that won’t be committed to the repository. Any rule you add to the `.git/info/exclude` file will not be committed and will only ignore files for your local repository.

## Global Rules

**File**: `~/.config/git/ignore`

You can tell Git to always ignore certain files or directories across commits in all Git repositories on your computer. These rules are added to the `~/.config/git/ignore` file.

---

[Git | gitignore Documentation](https://git-scm.com/docs/gitignore)

[GitHub Docs | Ignoring Files](https://docs.github.com/en/get-started/git-basics/ignoring-files)
