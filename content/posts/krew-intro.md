---
title: "Krew the Kubectl Plugin Manager"
description: "What drove me to create krew?"
date: 2018-08-08T12:14:00+02:00
cover:
  image: https://raw.githubusercontent.com/kubernetes-sigs/krew/master/assets/logo/horizontal/color/krew-horizontal-color.png
  relative: false
tags: ["intro","projects"]
draft: false
---

This summer I had an internship at Google, and it was awesome! I worked on an
open source project, which is now called
"[krew](https://github.com/GoogleContainerTools/krew)" a kubectl plugin manager.
I use krew to discover and install new plugins to my system. You should also
start to use a kubectl plugin manager because manual installation of plugins is
annoying.

<!-- ![demo](/img/demo_krew_intro.svg) -->


{{< figure align=center src="/img/demo_krew_intro.svg" caption="A small screencast demo of krew" title="">}}

## Kubectl Plugins!

If you had asked me 4 months before I wrote this, I would not be able to say if
kubectl plugins exist. However, kubectl plugins exist [since kubernetes
1.9](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG-1.9.md). And
apparently, plugins are fantastic: They help to organize commands under kubectl,
instead of having standalone binaries. The
[svcat](https://github.com/kubernetes-incubator/service-catalog/tree/master/cmd/svcat)
plugin is a great example.

Nonetheless, at the time of writing, almost no one knew about this kubectl plugin
subsystem. We determined this to be a problem of discoverability, as projects
were only advertising to be kubectl plugins on many project pages. Furthermore,
there was a lack of proper "Awesone kubectl plugin" pages, wich usually collect
all related information.

The second big factor was lifecycle management. Kubectl plugins used to be
installed manually for each project, leaving the downloading, upgrading, and
moving of the install binary to the end-user. Many of the end-users associate
this with too much friction, hindering the adoption of small plugins.

With krew we want to solve the problem of discoverability and lifecycle management, to fuel the kubernetes kubectl plugin ecosystem. Aiming to make it easier to find and install plugins and give plugin developers tool to easily deploy and deliver their projects to the user.

{{< figure align=center src="/img/krewlife.png" caption="Problem domains krew tries to solve." title="">}}

Krew does the following things for you:

1. Search and discover plugins
2. Check for compatibility with your system
3. Download, verify and install plugins
4. Keep plugins up-to-date

## Where to Start?

Install krew with a straight forward command form [the official guide](https://krew.sigs.k8s.io/docs/user-guide/setup/install/).

We have chosen a script to install krew, and it is not a bad thing. The formal reasoning
behind this decision was the simplicity of distributing a plugin over
using ten different package managers to reach all different platforms. We do not
rely on other software package managers because krew itself is a kubectl plugin
managed by krew. 

When looking at the last line of the install script, it can be observed that krew is a plugin itself: `"$KREW" install krew`. We call the temporarily downloaded krew to install itself.

Finally, once you got krew installed, you can install other plugins.

We now, to display the capabilities of krew, want to install the _ca-cert_ plugin.

```bash
kubectl plugin install ca-cert
```

* `kubectl plugin` is the command to call kubectl plugins.  

* `install` is a command that is introduced with krew.

Now we have `ca-cert` installed and can use it with:

```bash
kubectl plugin ca-cert
```



## Future

* It is essential for a healthy ecosystem to be versatile. That means, we can't
  only have a single centralized index (where plugin metadata is stored). We
  need to implement a model that allows [multiple index repositories](https://github.com/GoogleContainerTools/krew/issues/23). That allows
  users to install plugins which are not necessarily in the "main" default
  index. Think of it as a [PPA](https://launchpad.net/ubuntu/+ppas) or a "[brew
  tap](https://docs.brew.sh/Taps)".
* Another idea is to sync plugins with the cluster. That means whenever you
  connect to a kubernetes cluster the set of local plugins will adjust to the
  set of plugins defined in the cluster. The plugin spec was designed to be a
  kubernetes object. This will allow for such ideas. However, it is still a long
  way to implement this.
* We are currently trying to get krew into kubernetes as a constant part of
  kubectl. We have created a [Kubernetes Enhancement Proposal
  (KEP)](https://github.com/kubernetes/community/pull/2340), which aims to merge
  krew into kubectl. This means that you'll never have to install krew manually.

## TL;DR

* Krew is not standalone, integrates into kubectl
* We have an excellent tutorial, [check it out](https://github.com/GoogleContainerTools/krew/blob/master/docs/USER_GUIDE.md)!
* We need more plugins; the guide comes soon!
