# Git Aliases
Git aliases create shortcuts for frequently used git commands. Two ways to create an alias:

1. `git config` command
````buildoutcfg
    git config --global alias.co checkout
````

3. directly edit the git config file, `~/.gitconfig`, located in the user's `HOME` directoy


## Repos
````buildoutcfg

  f = fetch
  m = merge
  p = pull
  rv = remote -v

````

## Branching
````buildoutcfg
    nb = branch
    cob = checkout -b
    dlb = branch -D
````

# Workflow
````buildoutcfg

    # add files to staging
    a = add .
    
    # remove recently added files
    undo = reset HEAD~1 --mixed
    
    # check status
    s = status
    
    # standard commit
    cm = commit -m
    
    # routine commit for save point
    sv = "!git add -A && git commit -m 'chore: commit save point'"
    
    # commit for passing tests
    pt = "!git add -A && git commit -m 'passing tests'"
    
    # commit log
    graph = log --graph
    one = log --oneline
    
````


## Push
````buildoutcfg
    gpus = "!git push -u origin $(git current-branch)"
    
    unpublish = "!git push origin :$(git current-branch)"
````
