---
layout: default
title: "Home"
---

<p class=lead>Welcom to the Documentation site for <a href=http://team4405.com/>FRC Team 4405</a>. Here you will find detailed instructions on how to do almost anything related to the technical set up we have</p>

The template follows a very simple convention of defining categories that correspond to sections in the navigation. Here are the default ones (they are listed in the `_config.yml`):

- `doc` - Documentation
- `ref` - Reference
- `tut` - Tutorial
- `dev` - Developers
- `post` - Posts

Start by [creating a new post](http://jekyllrb.com/docs/posts/) one of the categories listed in `_config.yml`. It will appear in the navigation on the left once recompiled. Or use the supplied script to make creating pages easier:

```bash
ruby bin/jekyll-page "Some Page Title" ref
```

Read more [Usage]({{ site.baseurl }}{% post_url 2013-06-06-usage %}) page for more details or view the project [on GitHub](https://github.com/bruth/jekyll-docs-template/)
