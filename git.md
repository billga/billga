## Commands
### Global config
Global config makes it easy to set defaults:
`git config --global user.name "yourname"`  
`git config --global user.email "email@server"`  
`git config --global --list`  

### Ignore
Adding file patterns to a project's `.gitignore` will ignore for that project only, adding these to the global `.gitignore` and running the next command will enable it globally:
`git config –global core.excludesfile ~/.gitignore`
For instance, my global `.gitignore` has:
```text
.DS_Store
venv
.idea
.obsidian
```

### Sync transport
Switching from https to ssh in an *existing* project, just run: 
`git remote set-url origin git@github.com:repo/project.git` 

### Clone
Newly clone a project:
`git clone git@github.com:repo/project.git`

Other cmds:
`git status`  
`git branch -a`  *# list all branches*
`git add `_someNewFile.txt_  
`git commit -m "I'm committed to these changes"`  

Print a nice graph of all the commits and merges in the project:
`git log --graph --abbrev-commit --decorate --date=relative --oneline --all`

Preserve it for someone else:
`git push origin main`  
`git pull origin main`  

If your branch is stuck on `master`, go look at [[main|Fixing Main]].

## Aliases 
```shell
alias venv='source venv/bin/activate'
alias pug='pip3 install --upgrade pip'
alias gl='git log --graph --abbrev-commit --decorate --date=relative --oneline --all'
alias gitMod='git status | grep modified | sed "s/\(.*modified:\s*\)//"'
alias gitAddMod='git status | grep modified | sed "s/\(.*modified:\s*\)//" | xargs git add'
alias gs='git status'
alias gst='git status'
alias gsw='git switch'
alias gitRmDead='git ls-files --deleted -z | xargs -0 git rm'
alias gf='git fetch --all'
alias gb='git branch'
alias gitResetMain='git fetch --all && git checkout main && git reset --hard origin/main'
alias gitCurrent='git rev-parse --abbrev-ref HEAD'
```
