# billga
It's all about the meatware. No matter how much automation one has, human intellect is still needed to make it worthwhile.

`git version` # shows info about which `git` you're using  
`git config --global user.name "yourname"`  
`git config --global user.email "email@server"`  
`git config --global --list`  
`git clone `_github-https-url_  
`git status`  
`git branch develop` and `git branch -a`  
`git add `_someNewFile.txt_  
`git commit -m "I'm committed to these changes"`  
`git push origin master`  
and of course  
`git pull origin master`  

To create a virtualenv: 
`python3 -m venv [name]`
then: 
`source [name]/bin/activate`

## Master ⇢ Main
Lately, the term `master` was deprecated in favor of `main`. Newer `git` *should* default to `main`, but if it doesn't, follow the steps below.
### Changing from Remote
to change older git installations and swap the default branch name, do this:
```bash
$> git config --global init.defaultbranch main
$> git init 
$> git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
look for `On branch main`, if it's still on master, do the following. 
You have to add a file to give `git` something to do, then change the default branch name: 
```bash
$> touch tmp
$> git add tmp
$> git commit -m "moving from master to main"
[master (root-commit) bf9ce72] moving from master to main
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 tmp
$> git branch -m master main
$> git status 
On branch main
nothing to commit, working tree clean
```
Since the above was created remotely, you now must create and connect the origin to this new repo.
Follow the guidelines on github (or gitlab) to create a new repo, or go to the existing repo you want to connect and grab the `ssh` or `https` link to the repo. 
```bash
$> git remote add origin [paste link here]
$> git remote -v
$> git pull origin main --allow-unrelated-histories
$> git commit -m "linking remote to origin"
$> git push origin main
```
Et voilá!

### Changing from the Origin
On GitHub or GitLab, find the menu where it allows you to set the default branch. 

![Pasted_Image_11_23_21__1_28_PM](https://user-images.githubusercontent.com/6148844/143132119-2a9395fe-7958-477f-9826-3995eb36fe8f.png)

Select to edit, then change the default name to `main`:

![image](https://user-images.githubusercontent.com/6148844/143132286-4d6bb1ce-82a6-48b1-955d-d6f25fca8c63.png)

Back on your remote, run this to get your branches lined up.
```bash
$> git branch -m master main
$> git fetch origin
$> git branch -u origin/main main
$> git remote set-head origin -a
```
