Florian Begusch's terminal config

# [dot-files](https://github.com/diepfote/dot-files)
* [tmux config](https://github.com/diepfote/dot-files/blob/master/.tmux.conf)
* ... and anything else not in my bash script collection

# [bash script & source-me collection](https://github.com/diepfote/scripts)
## [helpers in go](https://github.com/diepfote/golang-tools)
* [source-me/bash-prompt.sh](https://github.com/diepfote/scripts/blob/3f150c0519b5ab020ac565aa5eebd2f471d057a9/source-me/bash-prompt.sh)
  sets PS1 (small golang program, why? faster than a script -> fast REPL)  
  and PROMPT_COMMAND (including `history` commands)
* [additional history control settings](https://github.com/diepfote/dot-files/blob/277ae930cbaa9a9261c176d8d4f7622d0ede4076/.bashrc#L6-L13) left in `.bashrc`.  

## [helpers in python](https://github.com/diepfote/python-tools)
### kubectl and oc bash completion patching  

What does this do? Includes `krew plugins` and [my own kubectl plugins](https://github.com/diepfote/scripts/tree/master/kubernetes/bin) in root command completion.
It also provides custom completion for [my own kubectl plugins](https://github.com/diepfote/scripts/tree/master/kubernetes/bin).

*additional root commands in completion*

```
$ oc
adm              auth             convert          diff             extract          label            new-project      port-forward     replace          scale            tag
annotate         autoscale        cp               edit             get              login            observe          process          rollback         secrets          version
api-resources    cancel-build     create           ex               idle             logout           options          project          rollout          serviceaccounts  wait
api-versions     cluster-info     debug            exec             image            logs             patch            projects         rsh              set              whoami
apply            completion       delete           explain          import-image     new-app          plugin           proxy            rsync            start-build
attach           config           describe         expose           kustomize        new-build        policy           registry         run              status
```
```
$ oc
adm                                  delete                               kustomize                            policy                               serviceaccounts
af-arbitrary-command                 delete-namespace-finalizer           label                                port-forward                         set
annotate                             describe                             login                                process                              sick-pods
api-resources                        diff                                 logout                               project                              start-build
api-versions                         edit                                 logs                                 projects                             status
apply                                ex                                   modify-secret                        proxy                                tag
attach                               exec                                 neat                                 rbac-lookup                          tmux-exec
auth                                 explain                              new-app                              registry                             topology
autoscale                            expose                               new-build                            replace                              ttsum
cancel-build                         extract                              new-project                          restart-af-services                  velero-annotate-all-volumes-for-pod
cluster-info                         fields                               node-shell                           rollback                             version
completion                           get                                  non-running-nodes                    rollout                              view-secret
config                               get-all-resources                    non-running-pods                     rsh                                  wait
convert                              idle                                 observe                              rsync                                warp
cp                                   image                                options                              run                                  watch-namespace
create                               images                               patch                                scale                                who-can
debug                                import-image                         plugin                               secrets                              whoami
```

*plugin commands option completion*

```
# yes I filtered which namespaces to display for this example

$ kubectl watch-namespace -n
openshift                          openshift-metrics-server
openshift-console                  openshift-node
openshift-infra                    openshift-template-service-broker
openshift-local-storage            openshift-web-console
openshift-logging
```

* kubectl 
  * [how to use](https://github.com/diepfote/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L124)  
  * where to find the [patch script](https://github.com/diepfote/python-tools/tree/master/kubectl-client)

* oc  
  * [how to use](https://github.com/diepfote/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L137)  
  * where to find the [patch script](https://github.com/diepfote/python-tools/tree/master/oc-client)

### miscellaneous
* [display ics calender files in plaintext](https://github.com/diepfote/python-tools/blob/master/show-ics.py)
* [convert latex editor Gummi snippets to Gedit snippets](https://github.com/diepfote/python-tools/blob/master/convert_gummi_snippets_to_gedit_snippets.py)


# git
* [aliases](https://github.com/diepfote/dot-files/blob/a2e4b1cc6bfe470d1c75760cb59665fec2b5c1ca/.gitconfig#L13)
* bash helpers
  * [general](https://github.com/diepfote/scripts/blob/3ac0081bbf178b4f9e630513e51c87bd8eee7527/source-me/posix-compliant-shells.sh#L589)
  * [linux only](https://github.com/diepfote/scripts/blob/703963f7ace80a5b61e182b09cb0884e547be436/source-me/linux/posix-compliant-shells.sh#L179)

# [vim config](https://github.com/diepfote/vim-config)
