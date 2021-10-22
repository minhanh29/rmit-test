## Initialize git
Go to the dir
git init
touch .gitignore  ->  ignore undesired files
(.DS_Store
 *.class)

## Create a new repository on the command line
curl -u 'minhanh29' https://api.github.com/user/repos -d '{"name":"<reponame>" (, "private":"true")}'
echo "Something" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/minhanh29/<reponame>.git
git push -u origin master


## Push
git add -A
git commit -m "Messages"
(git log -> show infor about repository changes)
git pull origin master  -> check if anyone made changes
git push origin master


## Create new branch
git branch [name]
git branch [-a]  -> check branch infor
git checkout [name]  -> switch branch
(or git checkout -b [name])
-> make changes
git add -A
git commit -m "Messages"
git push -u origin [name]
git checkout master
(git branch --merged  ->  show merged branches)
git merge [name]
git pull origin master
git push origin master


## Delete branches
git branch -d [name]
(git branch -a)
git push origin --delete [name]


## ignore all changes, go back to start
git checkout [filename]


## modify commit message
git commit --amend -m "New message"


## discard all changes
git checkout [file_name]


## change commit message
git commit --amend -m "New message"


## add a file to the last commit
git add [file_name]
git commit --amend
:q
git log --stat (to see the changes)
git log --all --graph --decorate --oneline (to see graph)


## copy a commit to [brach_name] branch
copy the hash code of the commit -> [hash]
git checkout [brach_name]
git cherry-pick [hash]


## reset a branch back to a certain commit
copy the hash code of the commit -> [hash]
	# soft: keep all changes and states
		git reset --soft [hash]
		git status
	# mix: default, keep all changes but go back to unstaged
		git reset [hash]
	# hard: discard all
		git reset --hard [hash]


## remove all untracked files
git clean -df  (d: all paths or directories, f: all files)


## recover some trash
git reflog  (print all worked commits)
copy the hash
git checkout [hash]
git branch backup   (save to 'backup' branch)
# check the recovery
	git checkout backup
	git log


## discard some changes without changing the history
git log
copy the hash of the commit to be undone
git revert [hash]
:wq
# check the status
	git log
	git diff [hash] [new_hash]


## transfer changes from master to sub-branch
git stash save "Changes"
git checkout [branch]
git stash pop
(or git stash apply stash@{ID})
git stash list (to see ID)
git stash drop stash@{ID}  (get rid of a stash)
git stash clear


## open difftool
(make some changes)
git difftool


## open merge tool
(the local and remote repos are changed, only the difference that is made by both repos is considred as "conflicts")
git checkout [branch]
git merge [other_branch]
git mergetool
git commit


## add options
add -A : add all files in all directories
add [dir] = add -A [dir]
add . = add -A .
add --no-all [dir] : add all except deleted files (that file still exists in remote repo)
add -u : add all except new files
add * : stupid, do not use

Source: https://www.youtube.com/watch?v=FdZecVxzJbk&list=PL-osiE80TeTuRUfjRe54Eea17-YfnOOAx&index=2
