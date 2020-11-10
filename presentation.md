# Overview
This presentation is meant to cover a couple Git commands I've found helpful in my day to day work. 
It assumes the viewer is familiar with the basics (cloning a repo, committing / pushing changes)

# Agenda
Commands to cover:
 - git rebase -i HEAD
 - git add -p 
 
 # git rebase interactive 
 https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History

## When to use this command?
Short answer: You need to rewrite history

### Scenario 1: 
 You've pushed your changes to a remote branch. The commit history looks like this:
 
 ```bash
 git log --oneline

82e5817 GVIL-0000 Bugfix 3 this time it really is fixed
4877d08 GVIL-0000 Bugfix 2 
cc0e442 GVIL-0000 Fixed the bug
 ```

You'd like to clean up the commit history

### Scenario 2:
You forgot the issue key in your commits and need to rewrite them

```bash
 git log --oneline

82e5817 Commit 3
4877d08 Commit 2
cc0e442 Commit 1
 ```

 # git add -p
 https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging

 ## When to use this command?
 You have changes that you want to break up into different commits

 ### Scenario:
 You've made several changes to a file; Some changes are related to a bugfix, some add support for a new feature

 ```yaml
 bugfix1:
 - line 1
 - line 2
 - line 3
feature:
 - line 1
 - line 2
bugfix2:
 - line 1
 - line 2
 - line 3
 ```
 You want to commit the bugfix1 changes in one commit, and the bugfix2 changes in another