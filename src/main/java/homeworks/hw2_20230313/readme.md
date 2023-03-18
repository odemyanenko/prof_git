Tasks
----------------
1. Как отказаться от изменений в файле (файлах) находящийся в рабочем каталоге (work directory)?
2. Как вернуть файл из индекса в рабочий каталог?
3. Как отменить ошибочный commit?
4. Как создать новую ветку и переключится в нее?
5. В чем отличение между fast-forward merge  and non fast-forward merge?
6. Когда может возникнуть конфликт слияния веток, как  его разрешить?
7. Можно ли удалить ветку? Как?

В ответах на вопросы 1-4, 7 необходимо указать конкретные команда git.
На 5 и 6 вопросы дать объяснение своими словами.

### Task 1
1. ```git checkout``` - cancel all changes
2. ```git checkout <file>``` - cancel changes in file
### Task 2
1. ```git restore --stage <file>```
   git-restore - Restore working tree files
### Task 3
1. ```git reset HEAD~1``` or ```git reset HEAD^``` 
   You have to specify the commit to undo in this case. 
   The last commit will be removed from your Git history.
### Task 4
1. create new branch and goto new branch
```
git branch <new_branch> 
git checkout <new_branch>
 ```
2. create and goto new branch
```
git checkout -b <new_branch>
``` 
### Task 5
1. ```non fast-forward merge```
   If master has diverged since the feature branch was created, the merging the feature branch into master will create a merge commit. This is the typical case.
2. ```fast-forward merge```
   If master has not diverged, instead of creating a new commit, git will then simply point master to the latest commit of the feature branch. This is a "fast forward".
3. [What Is a Git Merge Fast Forward?](https://blog.mergify.com/what-is-a-git-merge-fast-forward/)
### Task 6
1. If we changed files in our branch, when we merge ```git merge <our_branch>``` with a master that also had changes to those files, there may be a conflict where the git itself won't be able to handle the merging of file changes. This will create a new commit where we will have to fix the conflicting data ourselves.
2. [Git merge conflicts](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
3. [How to Resolve Merge Conflicts in Git – A Practical Guide with Examples](https://www.freecodecamp.org/news/resolve-merge-conflicts-in-git-a-practical-guide/)
### Task 7
1. ```git branch -d <branch>``` - delete branch with name <branch>. Before to do this we need to check out to other branch.
   