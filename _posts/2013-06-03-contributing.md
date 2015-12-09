---
layout: page
title:  Contributing
date:   2013-06-03 21:12:57
category: general
order: 0
---

In order to contribute to these docs, you must have an account on [Github](http://github.com) and be part of the [Team 4405](https://github.com/team4405) organization. To request access, please email [software@team4405.com](mailto:software@team4405.com) or talk to the software or buisness captain. 

### Updating

All of the articles are written in [Markdown](http://www.markitdown.net/markdown) (you can learn about it there) and are hosted on Githup pages. If you just want to edit a single page, you can:

1. Go to the [Repo](http://github.com/team4405/docs) 
2. Go to the `_posts` folder, 
3. Edit one of the posts. 

If you want to do more substantial development, clone the repo in your desktop, navigate to the folder and edit the content there. To enable the local development server, you must have the Prerequisites installed (see below) and then run `$ jekyll serve --watch` and navigate to [http://localhost:4000](http://localhost:4000) in your browser and you will have a live-reload server as you make changes. For more information about Jekyll, see the [Jekyll Documentation](http://jekyllrb.com/docs/home/).

#### Prerequisites

**Mac**
In order to run the local development server you need several things. If you are running this on a Mac or Linus (recommended) then make sure you have:

- [Ruby](http://ruby-lang.org/en/downloads) (including development headers, v1.9.3 or above for Jekyll 2 and v2 or above for Jekyll 3)
- [RubyGems](http://rubygems.org/pages/download)
- [NodeJS](http://nodejs.org)
- [Python](https://www.python.org/downloads/)

Then run the following:

`$ gem install jekyll`

**Windows**
If you are running Windows (not recommended), you need to first install [Chocalatey](https://chocolatey.org/) in order to be able to run Unix style commands. Then run:

- `choco install nodejs -y`
- `choco install ruby -y`
- `gem install jekyll`

Then you can run the development server on a windows machine. 

### Writing a New Post

Since Jekyll is more geared towards blog posts, specifiying a date and setting up the front-matter can get tedious. Supplied in the `bin` directory is a simple Ruby scripy for creating a new _page_:

```bash
ruby bin/jekyll-page title category [filename] [--edit]
```

where `title` is the title of page, `category` is one of the categories defined in the `_config.yml`. By default the `filename` will be derived from the `title`, but you can specify an explicit filename (without the date) by passing the third agument. Finally the `--edit` (or just `-e`) will launch the editor defined by the `$EDITOR` environment variable.

##### Example

```bash
./bin/jekyll-page "My New Page" general
```

Will produce a file `_posts/2013-06-05-my-new-page.md` with the [front-matter](http://jekyllrb.com/docs/frontmatter/) already defined:

```html
---
layout: page
title: "My New Page"
category: general
date: 2013-06-05 12:00:00
---
```

#### Navigation Order

Simply add an `order` attribute to the front-matter of the page and the navigation links will be sorted accordingly (within it's section).

```html
---
layout: page
title: "My New Page"
category: ref
date: 2013-06-05 12:00:00
order: 1
---
```

_Note: currently there is no way to arbitrarily order pages in Jekyll without the use of plugins. However, since deploying Jekyll sites to GitHub Pages is a common practice, we cannot rely on third-party plugins [since they are disabled](https://help.github.com/articles/pages-don-t-build-unable-to-run-jekyll#unsafe-plugins). This solution relies on JavaScript to sort the navigation after it has been rendered, so if JavaScript is disabled on the browser, the client is out of luck._


