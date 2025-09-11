Terminal Config

#### Table of contents

- [dot-files](#dot-files)
- [bash script & source-me collection](#bash-script--source-me-collection)
- [golang-tools](#golang-tools)
- [rust-tools](#rust-tools)
- [python-tools](#python-tools)
    - [extend kubectl bash completions/extend oc bash completions](#extend-kubectl-bash-completions)
    - [miscellaneous](#miscellaneous)
- [git](#git)
- [tmux](#tmux)
- [vimscript](#vimscript)


## dot-files

The config I use is split among several repos.
The main config is the [dot-files repo](https://github.com/diepfote/dot-files).  
It references the [scripts repo](#bash-script--source-me-collection) which in
turn references the [python-tools](#python-tools), [golang-tools](#golang-tools)
and [rust-tools](#rust-tools).

* [repo](https://github.com/diepfote/dot-files)
* [tmux config](https://github.com/diepfote/dot-files/blob/aed558943e888cc6b32eacdb9f64ca687f358869/.tmux.conf)

## bash script & source-me collection

Examples

<img src="./script-examples.png" width="600" />

* [repo](https://github.com/diepfote/scripts)

## golang-tools

Tools were I care about speed are not written in bash or python.
I instead tried go and zig and rust. For most of them I stuck to go.
I never considered c++ as I am not a fan and abstained from c as it
is harder to port between systems than aforementioned languages.

* [repo](https://github.com/diepfote/golang-tools)

### Use in tmux

Pane-border now display the current git branch and if it is in sync with the upstream branch (based on the last `git fetch`).  
Statusbar-right is used to display the current kubernetes cluster and openstack project.

* [pane-border](https://github.com/diepfote/dot-files/blob/aed558943e888cc6b32eacdb9f64ca687f358869/.tmux.conf#L51)
* [statusbar-right](https://github.com/diepfote/dot-files/blob/aed558943e888cc6b32eacdb9f64ca687f358869/.tmux.conf#L44)

## python-tools

As I am intimately familiar with python it is my go to programming language.
If the tasks cannot easily be accomplished in a scripting language and I
do not care about speed or I need it now, I will write it in python.

* [repo](https://github.com/diepfote/python-tools)

### extend kubectl bash completions

Kubectl does not provide functionality to add completions for
plugins or hand-rolled `kubectl-X_Y_Z` extensions.  
This is my [remedy](./kubectl-bash-completion-patching/index.html).

### miscellaneous

Here is a list of several things I needed or wanted to have
that might be of interest:

* [display ics calender files in plaintext](https://github.com/diepfote/python-tools/blob/2fef3537b26f8ce2b3019797460f5debbe9e17c4/show-ics.py)
* [convert latex editor Gummi snippets to Gedit snippets](https://github.com/diepfote/python-tools/blob/2fef3537b26f8ce2b3019797460f5debbe9e17c4/convert_gummi_snippets_to_gedit_snippets.py)
* [read toml setting](https://github.com/diepfote/python-tools/blob/f8a4e088de5e0b4b1694229f0162015adc9259a9/read_toml_setting.py)
* [urldecode/-encode](https://github.com/diepfote/python-tools/blob/5a79fd259c11ba860891b499a920e88b0fdda235/urlquoting.py)
* [regex substitution](https://github.com/diepfote/python-tools/blob/9c13477200e1db17c8768a328e2699437baf856f/regex-substitute.py)

## rust-tools

So far I only wrote a bash helper. It displays the current PATH, .venv, colors them
and shortens them so it is still readable if there are several tmux panes.  
After trying go and then zig I decided to see if rust would be even faster for the task.
I am sticking to it for now.  
I override the PROMPT_COMMAND [here](https://github.com/diepfote/scripts/blob/32000c108f5a6498b1c721151dee667adf078092/source-me/prompt.sh#L30).
Thus, anytime you hit Enter the PROMPT_COMMAND will use the [_ps1](https://github.com/diepfote/scripts/blob/32000c108f5a6498b1c721151dee667adf078092/source-me/prompt.sh#L30) function to set the `PS1` variable.
This variable is used by bash to display e.g. the current path.

## git

I decided to stick to plain git config for most functionality instead of writing separate bash helpers. The ones I use most often are `git find-commits-changed-file` and `git resubmit`.


* [aliases](https://github.com/diepfote/dot-files/blob/a2e4b1cc6bfe470d1c75760cb59665fec2b5c1ca/.gitconfig#L13)
* to edit the numerous git repos I use for my config I set up a bunch of bash functions to jump to these repos directly
  * [general](https://github.com/diepfote/scripts/blob/3ac0081bbf178b4f9e630513e51c87bd8eee7527/source-me/posix-compliant-shells.sh#L589)
  * [linux only](https://github.com/diepfote/scripts/blob/703963f7ace80a5b61e182b09cb0884e547be436/source-me/linux/posix-compliant-shells.sh#L179)
  * [autocompletion example](https://github.com/diepfote/scripts/blob/32000c108f5a6498b1c721151dee667adf078092/source-me/completions_golang.sh)

## vimscript

Please refer to [projects in vimscript](../projects/index.html#vimscript).  
My vim config: [repo](https://github.com/diepfote/.vim)

