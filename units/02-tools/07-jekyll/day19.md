# Jekyll

This week we are starting to use GitHub and Markdown to make web pages. We will be using a program called [Jekyll](http://jekyllrb.com/), which is a static site generator that lets you build a personal website, including a blog. It is tightly integrated with GitHub and, above all else, is free.

For today and Wednesday, we will be working with the GitHub webpage. On Friday, we will talk about how to work on Jekyll on your local computer.

## Getting Started

I have prepped two Jekyll themes for this class, to get you started:

* [Lanyon](https://github.com/oncomouse/lanyon)
* [Hyde](https://github.com/oncomouse/hyde)

You can use something else down the road, but these two are already set up to be fairly intuitive and work on GitHub.

Please fork which ever you prefer to use.

## Configuration

Once you have forked one of my two repos, make sure you are at your repo (and not mine (oncomouse's)).

### Site Configuration

There is a file called "_config.yml". Click on it and then edit it. This document is written in [YAML](http://lzone.de/cheat-sheet/YAML), a human-readable standard for data that Jekyll uses for configuration. In YAML everything from the start of the line to the first colon is called a **key**. The rest of the line is called a **value**. Key/value pairs are a very basic form of a database. I can ask this YAML file for value associated with the key "title" and it will give me "Lanyon".

We need to change the keys `url` and `baseurl`.

* `url` is set to `https://oncomouse.github.io`. Change `oncomouse` to your GitHub user name (which is the part of the page URL after "https://github.com/" and before the next "/"), but don't edit anything else.
* `baseurl` is either set to `'lanyon'` or `'hyde'`. Change it to `''`

Commit the file when you have changed these two things.

### Getting Online

Click on the "Settings" tab. At the top it should say "**Repository Name**". Change the text field (which should say either "lanyon" or "hyde") to "\<your-username\>.github.io" (the same value we set `url` to in `_config.yml`). Click "Rename".

When the page has reloaded, scroll down to "GitHub Pages". There should be a green box that says "Your site is published at `<url>`". If not, wait a few seconds and reload the page. If so, click the link.

You made a webpage!

## Creating Pages

Now that we have Jekyll working, we can create a new page on our site. If you aren't there, click the "Code" tab on your repo to acesss your site's code.

Click on `about.md` and click edit.

The file is basically a Markdown document, as we have been creating them, but the first four lines are special and let Jekyll find the file. Here they are:

~~~markdown
---
layout: page
title: About
---
~~~

This is called a YAML metadata block. It is data about the page (rather than the data itself, hence "meta"). There are two YAML key value pairs, one for `layout` and the other for `title`. The first tells Jekyll what kind of resource it is (it could be a blog post, for instance). The second tells our Jekyll theme what the page's title is.

You can edit the about.md page if you want to change some content on the site.

If you would like to add another page to your site, create a new file and name it whatever you want (but with a .md extension). So, for instance, if I want to make a contact page, I would create `contact.md` and add the following metadata block at the top:

~~~
---
layout: page
title: Contact Me
---
~~~

When I have saved the page, the link for my new contact page would be "http://oncomouse.github.io/contact.html" (the extension changes to HTML because web browsers don't understand Markdown and have to have it converted to HTML files for them).

*Note*: The Contact Me page will also be added to the sidebar menu in both Lanyon and Hyde themes. This is a feature of those themes, but is not standard to all Jekyll pages. If you use a different Jekyll theme in the future, make sure to check how to add page links to the navigation menu.

**Remember, every page _must_ have a metadata block to be built as a Jekyll page.**

## Blogging

Lanyon and Hyde are both set up, by default, as blogs (we'll talk about changing that on Wednesday). Posts are a special kind of page in Jekyll. They have to be placed in a specific folder and named a particular way.

### Creating the Post

A new blog post should be created in the `_posts` folder in your repo.

The file also needs to be named with the date it was created and some page information. Specifically, the format is:

~~~
YYYY-MM-DD-title.md
~~~

Where `YYYY` is the four-digit year (`2017`), `MM` is the two-digit month (`10`), `DD` is the two-digit day (`09`), and `title` is a version of the post's title that can only contain lowercase letters, numbers, and the hyphen (`-`).

If I was going to create a new post entitled "Hello World", the file would be named:

~~~
2017-10-09-hello-world.md
~~~

### Post Metadata

Now that we have our Markdown file, we need to add the YAML metadata block. There are a few additions for blog posts.

Unlike with pages, a post has the `layout` set to `post`. The `title` key is set to the blog post's title (so `title: Hello World`).

There is one additional key for blog posts, a `date` key.

`date` is the same date as the file name, but with a few additional elements:

~~~
YYYY-MM-DD HH:MM:SS
~~~

`YYYY`, `MM`, and `DD` are set as above. The `HH` is two-digit hour, `MM` is two-digit minute, and the `SS` is two-digit seconds.

So, my metadata block would be:

~~~
---
layout: post
title: Hello World
date: 2017-10-09 12:34:00
---
~~~

*Note*: If your blog post's title contains a colon or any complicated punctuation (commas, periods, ampersands, etc.), it is a good idea to put double quotes around the value, so that the metadata block would look like:

~~~
---
layout: post
title: "Hello World"
date: 2017-10-09 12:34:00
---
~~~

This will prevent errors in the future.
