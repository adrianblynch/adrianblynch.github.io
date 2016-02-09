---
layout: post
title: GitHub's 8 space tab problem and how to solve it
summary: 
tags: ['code style', 'github']
---

I'm a tabs over spaces man. When viewing code on GitHub, tabs are sized to 8 spaces. There are three ways to solve this issue.

1. Change your tab indents to spaces. Ermmm, no.
2. Append `?ts=4` to the URL. Manually? All the time? Ermmm, no.
3. Add display rules to a `.editorconfig` file. Ah!

GitHub will honour these settings if placed in a `.editorconfig` file in your repo.

```
root = true

[*]
indent_style = tab
indent_size = 4
```

[EditorConfig](http://editorconfig.org/) is an attempt to standardise IDE settings.

Thanks to [John Gardner](https://github.com/Alhadis) for [the quick answer](https://github.com/isaacs/github/issues/170#issuecomment-171555097).
