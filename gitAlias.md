= git Aliases
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
