Terminal Config

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

* [tmux config](https://github.com/diepfote/dot-files/blob/aed558943e888cc6b32eacdb9f64ca687f358869/.tmux.conf)
* ... and anything else not in my bash script collection

## bash script & source-me collection

Examples

<img src="./script-examples.png" width="600" />

[find here](https://github.com/diepfote/scripts)

## bash helpers in go

I use them in tmux statusbar & pane & PS1 for bash. [find here](https://github.com/diepfote/golang-tools)

Where I set them in bash:

* [source-me/bash-prompt.sh](https://github.com/diepfote/scripts/blob/3f150c0519b5ab020ac565aa5eebd2f471d057a9/source-me/bash-prompt.sh)
  sets PS1 (small golang program, why? faster than a script -> fast REPL)  
  and PROMPT_COMMAND (including `history` commands)
* [additional history control settings](https://github.com/diepfote/dot-files/blob/277ae930cbaa9a9261c176d8d4f7622d0ede4076/.bashrc#L6-L13) left in `.bashrc`.  

Where I set them in tmux:

* [pane-border](https://github.com/diepfote/dot-files/blob/aed558943e888cc6b32eacdb9f64ca687f358869/.tmux.conf#L51)
* [statusbar-right](https://github.com/diepfote/dot-files/blob/aed558943e888cc6b32eacdb9f64ca687f358869/.tmux.conf#L44)

## bash helpers in python

[find here](https://github.com/diepfote/python-tools)

### extend kubectl bash completions

[find here](./kubectl-bash-completion-patching/index.html)

### miscellaneous

* [display ics calender files in plaintext](https://github.com/diepfote/python-tools/blob/2fef3537b26f8ce2b3019797460f5debbe9e17c4/show-ics.py)
* [convert latex editor Gummi snippets to Gedit snippets](https://github.com/diepfote/python-tools/blob/2fef3537b26f8ce2b3019797460f5debbe9e17c4/convert_gummi_snippets_to_gedit_snippets.py)
* [read toml setting](https://github.com/diepfote/python-tools/blob/f8a4e088de5e0b4b1694229f0162015adc9259a9/read_toml_setting.py)
* [urldecode/-encode](https://github.com/diepfote/python-tools/blob/5a79fd259c11ba860891b499a920e88b0fdda235/urlquoting.py)
* [regex substitution](https://github.com/diepfote/python-tools/blob/9c13477200e1db17c8768a328e2699437baf856f/regex-substitute.py)


## git

* [aliases](https://github.com/diepfote/dot-files/blob/a2e4b1cc6bfe470d1c75760cb59665fec2b5c1ca/.gitconfig#L13)
* bash helpers
  * [general](https://github.com/diepfote/scripts/blob/3ac0081bbf178b4f9e630513e51c87bd8eee7527/source-me/posix-compliant-shells.sh#L589)
  * [linux only](https://github.com/diepfote/scripts/blob/703963f7ace80a5b61e182b09cb0884e547be436/source-me/linux/posix-compliant-shells.sh#L179)

## vim config

[find here](https://github.com/diepfote/.vim)

* [Plain vimscript](https://github.com/diepfote/.vim/blob/5000aabd9f3374db411f756f1f7d37c092a542f2/vimrc)
* [Plugin configuration and vimscript based on plugins](https://github.com/diepfote/.vim/blob/fa9c5cf84e1cf7530782229d262eacdda0fbdc52/plugins.vim)

