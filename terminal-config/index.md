## Florian Begusch's terminal config

### [dot-files](https://github.com/diepfote/dot-files)
* [tmux config](https://github.com/diepfote/dot-files/blob/master/.tmux.conf)
* ... and anything else not in my bash script collection

### [bash script & source-me collection](https://github.com/diepfote/scripts)
* [helpers in go](https://github.com/diepfote/golang-tools)
  * [source-me/bash-prompt.sh](https://github.com/diepfote/scripts/blob/3f150c0519b5ab020ac565aa5eebd2f471d057a9/source-me/bash-prompt.sh)
    sets PS1 (tiny golang program, why? faster than a script -> fast REPL)  
    and PROMPT_COMMAND (including `history` commands)
  * [additional history control settings](https://github.com/diepfote/dot-files/blob/277ae930cbaa9a9261c176d8d4f7622d0ede4076/.bashrc#L6-L13) left in `.bashrc`.  
    This has not been moved to put a `return` after the keybinding section
    in case I need to debug the config.  
    Otherwise my Bash History will be truncated or cleared.
* [helpers in python](https://github.com/diepfote/python-tools)
  * kubectl bash completion patching  
    [how to use](https://github.com/diepfote/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L124)  
    where to find the [patch script](https://github.com/diepfote/python-tools/tree/master/kubectl-client)
  * oc bash completion patching  
    [how to use](https://github.com/diepfote/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L137)  
    where to find the [patch script](https://github.com/diepfote/python-tools/tree/master/oc-client)

### git
  * [aliases](https://github.com/diepfote/dot-files/blob/a2e4b1cc6bfe470d1c75760cb59665fec2b5c1ca/.gitconfig#L13)
  * bash helpers
    * [general](https://github.com/diepfote/scripts/blob/3ac0081bbf178b4f9e630513e51c87bd8eee7527/source-me/posix-compliant-shells.sh#L589)
    * [linux only](https://github.com/diepfote/scripts/blob/703963f7ace80a5b61e182b09cb0884e547be436/source-me/linux/posix-compliant-shells.sh#L179)

### [vim config](https://github.com/diepfote/vim-config)
