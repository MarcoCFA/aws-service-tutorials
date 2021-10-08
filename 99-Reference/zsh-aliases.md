# ZSH Aliases
Aliases for the `zsh` CLI. All aliases located in the user's `HOME` directory in the file `/.zshrc`.

## Alias creation process
1. alias="command"
2. Open `/.zshrc` file

After creating the aliases, run the command `source ~/.zshrc` to activate them.

## CLI Aliases

````buildoutcfg
#----  ---#


````

## Python Aliases
````buildoutcfg
#---- virtualenv ----#
alias pystart="source .venv/bin/activate"


#----- Pip -----#
alias pip-install="pip install -r requirements.txt"
alias pip-list="pip freeze | less"
alias pip-search="pip freeze | grep -i"
alias pip-remove="pip uninstall"
alias pip-upgrade="pip install -U"
alias pip-upgrade-all="pip freeze --local | grep -v '^\-e' | cut -d = -f 1|xargs -n1 pip install -U"


#----- Documentation -----#
alias pydoc="python -m pydoc"


````

