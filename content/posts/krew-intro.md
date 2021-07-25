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

If you had asked me 4 months ago, I wouldn't be able to say if kubectl plugins
exist. However, kubectl plugins exist [since kubernetes
1.9](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG-1.9.md),
which is now almost a year ago. Plugins are fantastic: They help to organize
commands under kubectl. Instead of having standalone binaries. They can now be
integrated with kubectl. The
[svcat](https://github.com/kubernetes-incubator/service-catalog/tree/master/cmd/svcat)
plugin is a great example.

Krew does the following things for you:

1. Search and discover plugins
2. Check for compatibility with your system
3. Download, verify and install plugins
4. Keep plugins up-to-date

## Where to Start?

Install krew with this gist:

```bash
curl -SsL https://gist.githubusercontent.com/lbb/1256c790/raw/ | bash
```

We have chosen a script to install krew. It is not a bad thing. We don't rely on
other software package managers, because krew itself is a kubectl plugin managed
by krew.

Once you got krew installed, you can install other plugins.

Install the ca-cert plugin.

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
