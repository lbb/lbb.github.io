---
title: "Super Srt"
description: "Link Shortner on Steroids"
date: 2018-08-13T18:00:00+02:00
tags: ["intro","projects"]
draft: false
---

I saw several companies that had an internal tool that allows you to write short
links in your browser. Finally using such a tool at Google increased my
productivity by a lot. Think of short links on steroids, instead of using other
link services like "bit.ly" or "goo.gl" you can have links like `g/` for
github.com or `m/` for your mail. I've built a Chrome extension that allows you
to have such functionality in your browser, instead of setting up a private DNS.

> _"[...] AOL keywords for the corporate network."_
> Benjamin Staffin

## How it works

![Super Srt demo](/img/super_srt_demo.gif)

It is super simple to use.

Instead of organizing everything with link services you can use your browser as
a short linker. SuperSrt ships some redirect rules, such as `hn/` for hacker
news.

There are two types of rules:

1. Simple, typing just the short link `hn/` redirects you.
2. Search, adding something after the simple `hn/Super Srt` rule gets the
   appendix and inserts it with a regex into a different rule.

## Internals

Instead of using a company-wide DNS or a custom search engine (duckduckgo.com)
Super Srt as a Chrome plugin can intercept the HTTP requests. This has the
downside that routes won't be synced imidealty or that they are availiable to
everyone. But using a plugin is great for private users, that just want to
have the productivity gain.

 |Pro|Con
---|---|---
DNS| Instant Global Sync | Hard To Setup
Plugin|Easy To Setup|No or Slow Sync
The plugin checks
a dictionary with a O(1) lookup time for the entered URL. A matching URL will
hijack the current request and send an internal redirect to the Chrome engine.

```js
function matchRedirectFunc(details) {
       const url = new URL(details.url);
       const target = rules[url.host]; /*Lookup domain Rule, O(1)*/
       if (target != null) {
            return {
               redirectUrl: target.redirectUrl, /*Send redirect to engine*/
           };
       }
       return {}; /*Proceed with normal request*/
   }
```

The function now needs to be added as a middleware. The function needs to be
blocking to allow for the redirect of the request.

![Chrome Web Request](https://lh4.googleusercontent.com/zYMpDZFjk2mWGoTUOgwwTmiQ_ti5ixCL_Isi1-YWp0df2PN2GsL3KhBAhzm2VAW1GjbkE2x-v4ZKZ01OVg53Rap57mu73rdUX9py5298Fu2gVR339DIp7E6Zi9XQ54COqmvIku1W)

We need to register it at `onBeforeRequest`, which is called before a connection
is going to be made. We also can't restrict it so we have to make it available
for all domains.

```js
chrome.webRequest.onBeforeRequest.addListener(
        matchRedirectFunc,
        {urls: ["<all_urls>"]},
        ["blocking"],
);
```

## Mentions

Big thanks to the resources that gave me the inspiration to do this, check those
projects out:

* <https://github.com/kellegous/go> A DNS based `go/` link shortener
* <https://kev.inburke.com/kevin/url-shortener/> A DNS based short linker, the
  Readme gives a great explanation

## TL;DR

* Add the [Chrome Extension!](https://chrome.google.com/webstore/detail/super-srt/mjkmanccgpefafflmchghecahiocanfj)
* Source <https://github.com/lbb/SuperSrt>
