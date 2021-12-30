# OH MY ZSH configs and aliases


### ZSH configs
```
    ZSH_THEME="pygmalion"
    
    plugins=(
	    git
	    zsh-autosuggestions
    )

    source $ZSH/oh-my-zsh.sh
```


### Aliases
```
    export EDITOR='subl -w'
    alias ehosts='subl /etc/hosts'
    alias essh='subl ~/.ssh/'
    alias ezsh='subl ~/.zshrc'
    alias sites='cd ~/sites'
    alias gst='git status'
    alias dc='docker-compose'
    alias lsa='ls -lah'
    alias biggies="sudo find / -type f -printf '%s -  %t -  %p\n'| sort -nr | head -20"
    alias a2rs="systemctl reload apache2"

    boum() {
        free -h
        sudo sh -c "sync; echo 2 > /proc/sys/vm/drop_caches"
        docker ps --filter status=dead --filter status=exited -aq | xargs docker rm -v > /dev/null 2>&1;
        docker images --no-trunc | grep '<none>' | awk '{ print $3 }' | xargs -r docker rmi > /dev/null 2>&1;
        free -h
    }
```
