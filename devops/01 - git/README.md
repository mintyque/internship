## Prerequsite

* Git 2.28 or greater

## Tasks

* fork the current repository

* after passing other test tasks (02 - dockerfile, 03 - docker-compose, 04 - bash, 05 - cloud-ops) need to squash all your commits to one

* make a pull-request with the results of the tasks and tag Done-current date (e.g. `Done-01-01-2021`)


## Questions

1. What command can I use to view the commit history?
git log

2. What command can I use to undo the last commit?
git reset HEAD~1

3. What command can I use to create a new branch and a new tag?
git branch <branch_name>
git tag <tag_name>

4. How do I exclude a file / folder from a commit?
Add file to .gitignore to exclude it from future possible commits.
To exclude file from only current commit add ':!' e.g. git add --all -- :!dont_upload.txt

5. In case of a merge conflict, what commands can be used to resolve it?
To view the files that caused conflict: "git status"
To view commits that caused comflict: "git log --merge"
To undo changes to files: "git reset --merge"
Abort merge: "git merge --abort"

6. `*` What are pre-commit hooks and post-commit hooks, and what are they for?
Pre-commit and post-commit hooks are scripts that will be executed before and after commit respectively. Pre-commit hooks are usually executed to verify files and possibly modify commit.
Post-commit hooks cannot modify commits and are usually used for notifications.

7. `*` How do I change the last commit without adding a new commit?
git commit --amend
