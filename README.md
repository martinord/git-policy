# Git policy

This repo aims to describe **best practices** when using `git` version control, together with Github.

## Commit writing policy

When creating a new commit with `git commit -m "message"`, the author should write a short description, idealy **no longer than 50 characters**.

The rule of thumb is trying to form a sentence such as: *"This commit will \<commit-message\>"*. For example: `git commit -m "add a description of the header image in the about page"`.

This description should be preceeded with a prefix, identifying the type of change the commit makes in the repository. Here are the most used ones:

- **feat** – a new feature is introduced with the changes.
- **fix** – a bug fix has occurred.
- **chore** – changes that do not relate to a fix or feature and don't modify src or test files (for example updating dependencies).
- **refactor** – refactored code that neither fixes a bug nor adds a feature.
- **docs** – updates to documentation such as a the README or other markdown files.
- **style** – changes that do not affect the meaning of the code, likely related to code formatting such as white-space, missing semi-colons, and so on.
- **test** – including new or correcting previous tests.
- **perf** – performance improvements.
- **ci** – continuous integration related.
- **build** – changes that affect the build system or external dependencies.
- **revert** – reverts a previous commit.

As an example, when creating a new feature by adding changes to several files, the commit message could be: `git commit -m "feat: add button to allow the user sending an email"`. 

## Working with branches

When making changes that require several commits but are linked with a feature, it is a good practice to use branches. 

To create a branch and upload it we can do the following:
```bash
# Create branch
git branch new-branch
git switch new-branch
# Add commit and push branch for first time
git add .
git commit -m "feat: add a new feature for foo in bar"
git push -u origin new-branch
# Future pushes to the remote repo
git push
```

When we are finished with all commits, we can merge this changes in the `main` branch. This can be done in several ways, but to avoid a commit that only merges changes, and keep a clean git history, we can do the following:

```bash
# Last commit has been done, now switch to main branch
git switch main
# Add the last commits of the branch on top of the main branch
git rebase new-branch
```

## Credits

This git policy has been created by [Martiño Rivera-Dourado](https://martinord.eu) and published at [Github](https://github.com/martinord/git-policy).