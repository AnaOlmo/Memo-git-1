

# DOCUMENT ELEVE / GIT

Fiche mémo

# Les commentaires

| EXPRESSION | A QUOI CA SERT ? | EXEMPLE D&#39;UTILISATION |
| --- | --- | --- |
| **git init** | (Créer un nouveau projet vide sur un dépôt GIT vide)- folder not using Git yet, create one | [**Create a new local repository**](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-init?_ga=2.40175906.1428782082.1512654050-1258256408.1512654050) |
| **git status** | Status project - List the files you've changed and those you still need to add or commit: | [**Status**](https://www.atlassian.com/git/tutorials/inspecting-a-repository?_ga=2.78514068.1428782082.1512654050-1258256408.1512654050#git-status) |
| **git Log** | Check  Commit history |   |
| **git Push** ( **git push origin master** ) **git push -u origin master** | Send last version to GitHub - Send changes to the master branch of your remote repository:-u : remembers the parameters | [**Push**](https://www.atlassian.com/git/tutorials/syncing?_ga=2.49809318.1428782082.1512654050-1258256408.1512654050#git-push) |
| **git Commit** git commit -m &quot;Commit message&quot;git commit -a | Commit changes to head (but not yet to the remote repository):Commit any files you&#39;ve added with git add, and also commit any files you've changed since then: | [**Commit**](https://www.atlassian.com/git/tutorials/saving-changes?_ga=2.78514068.1428782082.1512654050-1258256408.1512654050#git-commit) |
| **git Add** git add 'filename'; **git add  '*.txt'** | Add a file to next Commit **Add one or more files to staging (index):** | [**Add files**](https://www.atlassian.com/git/tutorials/saving-changes?_ga=2.11477300.1428782082.1512654050-1258256408.1512654050#git-add) |
| **git add -A** | Add all files created or modify to next Commit |   |
| **git reset HEAD**** (**Git reset HEAD file/to/remove.txt) | Remove a file added before a Commit |   |
| **git cd** | Check directory |   |
| **git ls** | See list |   |
| **git CP** | copy |   |
| **git PWD** | Where we are in our tree |   |
| **git ls / git ls-a** | See hidden .Git folders in GIT |   |
| git clonegit clone /path/to/repository | **Create a working copy of a local repository:** | [**Check out a repository**](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-clone?_ga=2.18836409.1428782082.1512654050-1258256408.1512654050) |
| Git diffgit diff HEADgit diff  --staged | See changes made but not part of staging area (green = added / red = removed)most recent commitSee changes made in staged elements (already committed) |   |

| Git remote **git remote add origin <server>;**** git remote -v **|** If you haven't connected your local repository to a remote server, add the server to be able to push to it: ****List all currently configured remote repositories** | [**Connect to a remote repository**](https://www.atlassian.com/git/tutorials/syncing#git-remote) |
| --- | --- | --- |
| Git checkoutgit checkout -b <branchname>;git checkout <branchname>;git branchgit branch -d <branchname>;git push origin <branchname>;git push --all origingit push origin <branchname>; **git checkout <commit>;** | **Permet de transformer le** fichier**tel qu'il était lors du** commit **et l'ajoute au** _staging_ **.**** Create a new branch and switch to it:**Switch from one branch to another:List all the branches in your repo, and also tell you what branch you're currently in:Delete the feature branch:Push the branch to your remote repository, so others can use it:Push all branches to your remote repository:Delete a branch on your remote repository:Transforme tous les fichiers pour reproduire l'état du commit. Cette commande nous place dans un état particulier appellé _detached HEAD_. En résumé vous êtes revenu en arrière en tant que spectateur. Vous pouvez voir le projet tel qu'il était au moment du commit tout en ayant la possibilité de revenir dans le _présent_. On utilisera cette commande pour observer des vieux commit, si on souhaite réellement revenir en arrière on utilisera plutôt la commande _reset_. | [**Branches**](https://www.atlassian.com/git/tutorials/using-branches?_ga=2.16207542.1428782082.1512654050-1258256408.1512654050) |
| **git pull** | Fetch and merge changes on the remote server to your working directory: | [**Update from the remote repository**](https://www.atlassian.com/git/tutorials/syncing?_ga=2.106786691.1428782082.1512654050-1258256408.1512654050) |
| git merge &lt;branchname&gt; | To merge a different branch into your active branch: |   |
| **git diff**** git diff --base filename**git diff sourcebranch; targetbranch; | View all the merge conflicts:View the conflicts against the base file:Preview changes, before merging: |   |
| git add filename | After you have manually resolved any conflicts, you mark the changed file: |   |
| git tag 1.0.0 <commitID>; | You can use tagging to mark a significant changeset, such as a release: | **Tags** |

| git log | CommitId is the leading characters of the changeset ID, up to 10, but must be unique. Get the ID using: |   |
| --- | --- | --- |
| git push --tags origin | Push all tags to remote repository: |   |
| git checkout -- &lt;filename&gt;git checkout -b   new\_branch | If you mess up, you can replace the changes in your working tree with the last content in head:Changes already added to the index, as well as new files, will be kept.All at once | [**Undo local changes**](https://www.atlassian.com/git/tutorials/undoing-changes?_ga=2.83256854.1428782082.1512654050-1258256408.1512654050) |

| git fetch origingit reset --hard origin/master | Instead, to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it, do this: |   |
| --- | --- | --- |
| **git grep foo()** | Search the working directory for foo(): | **Search** |
| **git revert commit** | **Revert** permet ;inverser un commit. Cette commande va défaire ce qui avait été fait au moment du &lt;commit&gt; en créant un nouveau commit. Cela ;altère pas ;historique mais va ajouter un nouveau commit ;inversion (les lignes ajoutées seront supprimées, les fichiers supprimés seront recréés...). |   |

| **git reset fichier**** git reset ****git reset --hard** | ** reset** permet de faire plusieurs choses à la fois. En revanche il faudra faire très attention lors de ;utilisation de cette commande car elle altère ;historique et peut dans certains cas supprimer vos modifications (si vous voyez --hard, vérifiez 6 fois ce que vous voulez faire).Supprime un fichier de la zone de staging, mais ne supprime pas les modifications qui sont faites Supprime tous les fichiers de la zone de staging, sans supprimer les modifications.Cette commande est à utiliser avec **extrème précaution** , elle renvoit le dossier de travail au niveau du dernier commit. Toutes les modifications non commit seront perdues. |   |
| --- | --- | --- |
| **git rm**** git rm '*.txt'** | Removing all files |   |
| **Git show** | Check content of file |   |

|   |   |   |
| --- | --- | --- |
|   |   |   |
|   |   |   |
|   |   |   |
|   |   |   |

