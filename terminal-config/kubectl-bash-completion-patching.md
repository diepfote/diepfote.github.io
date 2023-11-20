# Extend kubectl bash completions/extend oc bash completions

e.g. add bash completions for krew plugins

#### Table of contents

- [What does this do?](#what-does-this-do)
- [Examples](#examples)
- [Where to find](#where-to-find)

## What does this do?

Includes `krew plugins` and [my own kubectl plugins](https://github.com/diepfote/scripts/tree/ff979559100101fe7e824e83d2bda84a58a3ecc4/kubernetes/bin) in root command completion.
It also provides custom completion for [my own kubectl plugins](https://github.com/diepfote/scripts/tree/ff979559100101fe7e824e83d2bda84a58a3ecc4/kubernetes/source-me).

## Examples

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

## Where to find

* kubectl 
  * [how to use](https://github.com/diepfote/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L124)  
  * where to find the [patch script](https://github.com/diepfote/python-tools/tree/146f57d759cb7ed26c6713c7eb1e1cf5be644654/kubectl-client)

* oc  
  * [how to use](https://github.com/diepfote/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L137)  
  * where to find the [patch script](https://github.com/diepfote/python-tools/tree/f42b18945544c7648ce517ce1024ff213ed0d190/oc-client)

  ---

  by Florian Sorko
