# git

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

## Aliases 
```shell
alias venv='source venv/bin/activate'
alias pug='pip3 install --upgrade pip'
alias gl='git log --graph --abbrev-commit --decorate --date=relative --oneline --all'
alias gitModified='git status | grep modified | sed "s/\(.*modified:\s*\)//"'
alias gitAddModified='git status | grep modified | sed "s/\(.*modified:\s*\)//" | xargs git add'
alias gs='git status'
alias gst='git status'
alias gsw='git switch'
alias gitRmDead='git ls-files --deleted -z | xargs -0 git rm'
alias gf='git fetch --all'
alias gb='git branch'
alias gitResetMain='git fetch --all && git checkout main && git reset --hard origin/main'
alias gitCurrent='git rev-parse --abbrev-ref HEAD'
```
