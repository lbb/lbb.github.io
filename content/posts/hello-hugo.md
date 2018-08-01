---
title: "Hello Hugo!"
description: "Saying 'Hello' from Hugo"
date: 2014-09-01T12:19:03+08:00
tags: ["hugo","blog"]
draft: true
---

Hello from Hugo! If you're reading this in your browser, good job! The file `content/post/hello-hugo.md` has been converted into a complete HTML document by Hugo. Isn't that pretty nifty?

A Section
---------

Here's a simple titled section where you can place whatever information you want.

You can use inline HTML if you want, but really there's not much that Markdown can't do.

Showing off with Markdown
-------------------------

A full cheat sheet can be found [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
or through [Google](https://google.com/).

There are some *easy* examples for styling, though. I can't **emphasize** that enough.
Creating [links](https://google.com/) or `inline code` blocks are very straightforward.

```
There are some *easy* examples for styling, though. I can't **emphasize** that enough.
Creating [links](https://google.com/) or `inline code` blocks are very straightforward.
```

Front Matter for Fun
--------------------

This is the meta data for this post. It is located at the top of the `content/post/hello-hugo.md` markdown file.

```
---
title: "Hello Hugo!"
description: "Saying 'Hello' from Hugo"
date: "2014-09-01"
categories:
  - "example"
  - "hello"
tags:
  - "example"
  - "hugo"
  - "blog"
---
```

This section, called 'Front Matter', is what tells Hugo about the content in this file: the `title` of the item, the
`description`, and the `date` it was posted. In our example, we've added two custom bits of data too. The `categories` and
`tags` sections are used in this example for indexing/grouping content. You will learn more about what that means by
examining the code in this example and through reading the Hugo [documentation](http://gohugo.io/overview/introduction).

---
__Advertisement :)__

- __[pica](https://nodeca.github.io/pica/demo/)__ - high quality and fast image
  resize in browser.
- __[babelfish](https://github.com/nodeca/babelfish/)__ - developer friendly
  i18n with plurals support and easy syntax.

You will like those projects!

---

# h1 Heading 8-)
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading


## Horizontal Rules

___

---

***


## Typographic replacements

Enable typographer option to see result.

(c) (C) (r) (R) (tm) (TM) (p) (P) +-

test.. test... test..... test?..... test!....

!!!!!! ???? ,,  -- ---

"Smartypants, double quotes" and 'single quotes'


## Emphasis

**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~


## Blockquotes


> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.


## Lists

Unordered

+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar


## Code

Inline `code`

Indented code

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code


Block code "fences"

```
Sample text here...
```

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

## Tables

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

Right aligned columns

| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |


## Links

[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)


## Images

![Minion](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"


## Plugins

The killer feature of `markdown-it` is very effective support of
[syntax plugins](https://www.npmjs.org/browse/keyword/markdown-it-plugin).


### [Emojies](https://github.com/markdown-it/markdown-it-emoji)

> Classic markup: :wink: :crush: :cry: :tear: :laughing: :yum:
>
> Shortcuts (emoticons): :-) :-( 8-) ;)

see [how to change output](https://github.com/markdown-it/markdown-it-emoji#change-output) with twemoji.


### [Subscript](https://github.com/markdown-it/markdown-it-sub) / [Superscript](https://github.com/markdown-it/markdown-it-sup)

- 19^th^
- H~2~O


### [\<ins>](https://github.com/markdown-it/markdown-it-ins)

++Inserted text++


### [\<mark>](https://github.com/markdown-it/markdown-it-mark)

==Marked text==


### [Footnotes](https://github.com/markdown-it/markdown-it-footnote)

Footnote 1 link[^first].

Footnote 2 link[^second].

Inline footnote^[Text of inline footnote] definition.

Duplicated footnote reference[^second].

[^first]: Footnote **can have markup**

    and multiple paragraphs.

[^second]: Footnote text.


### [Definition lists](https://github.com/markdown-it/markdown-it-deflist)

Term 1

:   Definition 1
with lazy continuation.

Term 2 with *inline markup*

:   Definition 2

        { some code, part of Definition 2 }

    Third paragraph of definition 2.

_Compact style:_

Term 1
  ~ Definition 1

Term 2
  ~ Definition 2a
  ~ Definition 2b


### [Abbreviations](https://github.com/markdown-it/markdown-it-abbr)

This is HTML abbreviation example.

It converts "HTML", but keep intact partial entries like "xxxHTMLyyy" and so on.

*[HTML]: Hyper Text Markup Language

### [Custom containers](https://github.com/markdown-it/markdown-it-container)

::: warning
*here be dragons*
:::


# Krew

## Table of Contents
* [Krew](#krew)
  * [Table of Contents](#table-of-contents)
  * [Summary](#summary)
  * [Motivation](#motivation)
    * [Discoverability](#discoverability)
    * [Cross-platform Packaging](#cross-platform-packaging)
    * [Lifecycle management](#lifecycle-management)
    * [Goals](#goals)
    * [Non-Goals](#non-goals)
  * [Proposal](#proposal)
      * [Capabilities](#capabilities)
    * [Scenarios (standalone only)](#scenarios-standalone-only)
    * [Scenarios](#scenarios)
    * [UX and CLI Flow](#ux-and-cli-flow)
    * [Implementation Details/Notes/Constraints](#implementation-detailsnotesconstraints-optional)
    * [Risks](#risks)
  * [Graduation Criteria](#graduation-criteria)
  * [Implementation History](#implementation-history)
  * [Drawbacks](#drawbacks)

## Summary

krew is a package manager for the kubectl plugin system. krew introduces a way
to handle kubectl plugin management and discovery.

## Motivation

The kubectl plugin system allows users to extend kubectl by placing extension
executables in a plugin directory. This allows new subcommands and subcommand
trees to be added in the kubectl CLI interface under `kubectl plugin <NAME>`.
This has the following user friction:

* Users need to manually download and manage plugins to ~/.kube/plugins and
  keep them up to date
* Users need to be aware of the installation requirements and instructions of
  each plugin

Currently, there are no unified distribution methods for kubectl plugins.
This has several disadvantages:

### Discoverability

Available kubectl plugins are not easily discoverable and searchable.

### Cross-platform Packaging

Plugins need to be packaged separately different OS and distros.
Often, plugin maintainers do not do this.

### Lifecycle management 

Often installation is done through manually downloading a zip and placing
it under ~/.kube/plugins. This is an unpleasant experience to the user
especially when it comes to updating the plugins,
or when a user deletes ~/.kube.

---

Those disadvantages will lead to slow the adoption rate of kubectl plugins.
krew will be a plugin manager able to solve all of the named issues. 

### Goals


* Install, uninstall and update plugins
* Discovery of plugins
* Giving developers a platform to contribute their plugins to
* Build repository platform for contributors (i.e brew formulas approach)
* Allow multiple plugin index sources
* (only for standalone) Self hosting: krew installation doesn't require a
  package manager: it can upgrade itself 

### Non-Goals

* Dependency management of libraries
* Plugins are user facing programs, they should not depend on each other.
  They have environment requirements like curl or git.
  Krew is not responsible to cover external dependency,
  program and environment setup like apt,
  brew or dnf. The user will be informed to take action.
* Complete integration with various download sources like “hg://” or “samba://”
* kubectl version compatibility management


## Proposal

#### Capabilities

Note: This proposal has already been implemented in
`github.com/GoogleContainerTools/krew` as a proof of concept.
The goal is to move it into kubectl.

Define a new meta config format called plugin manifest
(stored in the index under: <plugin-name>.yaml)


### Scenarios (standalone only)

* User wants to install krew. They can run one `curl` command to install the
  plugin manager, the plugin manager should then be able to function properly.

### Scenarios

* User wants to install and update a plugin.
  They use the search to discover plugins `kubectl plugin search foo`.
  Every plugin displays a short description of its purpose.
  They find the right plugin and install it with the install command.
  Using the update command them can update all installed plugins to it
  latest version. 
* User moves to a new machine and wants to reinstall all their plugins.
  They can copy the declarative plugin list. This file contains all plugins that
  were requested by the user to be installed. They have to copy it to the new
  installation and run an update. There will be a command for exporting and
  importing depots.
* Developer wants to make his plugin discoverable by others.
  They provide a link to the whole plugin as a compressed file under a public
  URL. (Github provides any commit/tag as .tar.gz automatically.)
  Afterwards the developer creates a PR against the index repository with a new
  meta description file. This file contains the download url, download hash,
  plugin version and description and tags. Meta descriptions are used by the
  plugin manager to discover and manage plugins.
* Developer wants to update their plugin and make those changes public.
  They create a new PR against the index repository updating their plugin meta
  description file. 

### UX and CLI Flow 

```text
# Update and fetch plugin index.
$ kubectl plugin update

# Search for plugins
$ kubectl plugin search servicecat
service-catalog     Consume services in Kubernetes using the Open S... available
service-cat-viewer  Show ASCII cat picture for every Service format... installed  
service-catalog-gke A helper utility for discovering GKE services l... available

$ kubectl plugin info service-cat-viewer
DESCRIPTION: Show ASCII cat picture for every Service formatet ISO-11801
URL: https://github.com/oscar-kitty/viewer.git

CAVEATS:
This plugin needs the following programs:
* fzf
* jq

For a better user experience:
  export $TERM=vt220

# Install the plugin.
$ kubectl plugin install service-cat-viewer
Installation (1/1): service-cat-viewer
Downloading https://github.com/oscar-kitty/viewer.git
Progress: 100%
Done!

Plugin Caveats:
  This plugin needs the following programs:
  * fzf
  * jq

  For a better user experience:
    export $TERM=vt220

# Update all plugins and index
$ kubectl plugin upgrade

# Update specific plugins
$ kubectl plugin upgrade foo bar

# uninstall plugin
$ kubectl plugin remove aws-cat-viewer

# Store the list of installed plugins
$ kubectl plugin list > deposit.txt

# On a new machine load the plugin list
$ kubectl plugin install < deposit.txt
... [Plugin installation output] ...
```

### Implementation Details/Notes/Constraints

krew has already been implemented in the `github.com/GoogleContainerTools/krew`
repo, and should be moved to a separate repo for the sub project.
krew was initially developed as its own cli, however once it has matured,
it should be published as a subcommand of kubectl or as a statically linked
plugin. It should also be more tightly integrated with apply.

### Risks
The index repository needs some form of governance to prevent malicious plugins. 

## Graduation Criteria
* Dogfood krew by either:
  * moving one or more of the cncf clis to it (i.e helm)
  * getting user feedback from one or more mid or large application deployments
    using krew.
* Publish krew as a subcommand of kubectl.


## Implementation History
krew was implemented in the `github.com/GoogleContainerTools/krew` repo before
subprojects became a first class thing in Kubernetes. The code has been fully
implemented, but it must be moved to a proper location.

## Drawbacks

Implementing krew and growing the ecosystem can hold back the git-style plugin
approach.
