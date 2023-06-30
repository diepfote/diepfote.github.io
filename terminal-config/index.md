Florian Sorko's terminal config

#### Table of contents

- [dot-files](#dot-files)
- [bash script & source-me collection](#bash-script--source-me-collection)
- [bash helpers in go](#bash-helpers-in-go)
- [bash helpers in python](#bash-helpers-in-python)
    - [extend kubectl bash completions/extend oc bash completions](#extend-kubectl-bash-completions)
    - [miscellaneous](#miscellaneous)
- [git](#git)
- [vim config](#vim-config)


## dot-files

[find here](https://github.com/diepfote/dot-files)

* [tmux config](https://github.com/diepfote/dot-files/blob/master/.tmux.conf)
* ... and anything else not in my bash script collection

## bash script & source-me collection

[find here](https://github.com/diepfote/scripts)

## bash helpers in go

[find here](https://github.com/diepfote/golang-tools)
* [source-me/bash-prompt.sh](https://github.com/diepfote/scripts/blob/3f150c0519b5ab020ac565aa5eebd2f471d057a9/source-me/bash-prompt.sh)
  sets PS1 (small golang program, why? faster than a script -> fast REPL)  
  and PROMPT_COMMAND (including `history` commands)
* [additional history control settings](https://github.com/diepfote/dot-files/blob/277ae930cbaa9a9261c176d8d4f7622d0ede4076/.bashrc#L6-L13) left in `.bashrc`.  

## bash helpers in python

[find here](https://github.com/diepfote/python-tools)

### extend kubectl bash completions

[find here](./kubectl-bash-completion-patching.html)

### miscellaneous
* [display ics calender files in plaintext](https://github.com/diepfote/python-tools/blob/master/show-ics.py)
* [convert latex editor Gummi snippets to Gedit snippets](https://github.com/diepfote/python-tools/blob/master/convert_gummi_snippets_to_gedit_snippets.py)


## git
* [aliases](https://github.com/diepfote/dot-files/blob/a2e4b1cc6bfe470d1c75760cb59665fec2b5c1ca/.gitconfig#L13)
* bash helpers
  * [general](https://github.com/diepfote/scripts/blob/3ac0081bbf178b4f9e630513e51c87bd8eee7527/source-me/posix-compliant-shells.sh#L589)
  * [linux only](https://github.com/diepfote/scripts/blob/703963f7ace80a5b61e182b09cb0884e547be436/source-me/linux/posix-compliant-shells.sh#L179)

## vim config
[find here](https://github.com/diepfote/.vim)
