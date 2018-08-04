---
title: "Mirage OS"
description: "Cross post from mirgaeOS"
date: 2018-08-10T12:13:00+02:00
tags: ["conference", "mirageOS","OCaml", "report"]
draft: false
---

This is a cross port from the mirgaeOS Blog. We have been on a hack retreat in
Morocco to hack on an OCaml unikernel Operating System. Go to the official
[mirageOS Blog](https://mirage.io/blog/2017-march-hackathon-roundup) to read
more amazing articles.

## Original Post

“Let’s make operating systems great again” – with this in mind we started our
trip to Marrakech. But first things first: we are two first year computer
science students from Berlin with not a whole lot of knowledge of hypervisors,
operating systems or functional programming. This at first seems like a problem…
and it turned out it was :). The plan was set, let’s learn this amazing language
called OCaml and start hacking on some code, right? But, as you could imagine,
it turned out to be different yet even better experience. When we arrived, we
received a warm welcome in Marrakech from very motivated people who were happy
to teach us new things from their areas of expertise. We wanted to share some of
our valuable knowledge as well, so we taught some people how to play Cambio, our
favourite card game, and it spread like wildfire (almost everyone was playing it
in the second evening). We’re glad that we managed to set back productivity in
such a fun way. ;P

Back to what we came to Morocco for: as any programming language, OCaml seems to
provide its special blend of build system
challenges. [Rudi](https://github.com/rgrinberg/) was kind enough to help us
navigate the labyrinth of distribution packages, opam, and ocamlfind with great
patience and it took us only two days to get it almost right.

Finally having a working installation, we got started by
helping [Michele](https://github.com/mmaker/) with
his [ocaml-acme](https://github.com/mmaker/ocaml-acme/) package, a client for
Let's Encrypt (and other services implementing the protocol). An easy to use and
integrate client seemed like one feature that could provide a boost to unikernel
adoption and it looked like a good match for us as OCaml beginners since there
are many implementations in other programming languages that we could refer to.
After three days we finally made our first Open Source OCaml contributions to
this MirageOS-related project by implementing the dns-01 challenge.

Hacking away on OCaml code of course wasn’t the only thing we did in Marrakech:
we climbed the Atlas mountains to see the seven magic waterfalls (little
disclaimer: there are only four). It was not a really productive day but great
for building up the spirit which makes the community so unique and special.
Seeing camels might also helped a little bit. ;)

One of the most enjoyable things that the retreat provided was the chance for
participants to share knowledge through presentations which lead to very
interesting conversations like
after [Amir’s](https://github.com/amirmc/) presentation when some artists asked
about sense of life and computer systems (by the way, one question is already
solved and it is ’42’). We were also very impressed by the power and
expressiveness of functional languages
which [Sprios](https://github.com/seliopou/) demonstrated in his parser
combinator [Angstrom](https://github.com/inhabitedtype/angstrom/).

Thank you to everyone involved for giving us the experience of an early
‘enlightenment’ about functional programming as first year students and the
engaging discussions with so many amazing people! We sure learned a lot and will
continue working with OCaml and MirageOS whenever possible.

Hope to see all of you again next time!