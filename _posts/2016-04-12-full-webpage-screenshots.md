---
layout: post
title: Getting Full Webpage Screenshots
category: code
---

Found Paul Hammond's delightful [webkit2png](http://www.paulhammond.org/webkit2png/) command line tool today. Things I tried before:

1. Chrome extensions: absolutely awful rendering
2. Safari 'save as PDF': close but with weird janky css
3. Casper: much more involved and never quite right either.

webkit2png renders really well. It's a little slow, but could be worse. To make my life a bit easier, I wrote a little bash function. Obviously the `pbpaste` part only works on Mac, but I'd imagine Linux has its own.

```sh
function fullshot {
    webkit2png --ignore-ssl-check -F -o $1 `pbpaste`
}
```

And now, when I need to screenshot something, I copy the link into my clipboard and type `fullshot filetitle`. Done!
