lang: es
publish: false
tags:
- mi motor de blog
- código abierto
date: 2019-07-10 01:20:03.829830919 +00:00

---


# Como enviar un pull request a mis entradas

_If you see a typo or information that you believe is not true, you can go ahead and fix it yourself! I always welcome feedback and contributions. This short post explains how to do it._

If you ever contributed to any OSS, you already know the drill: fork the [repo](https://github.com/botanicus/data.blog), make changes, run tests and submit a pull request.

## Which file to edit?

Firstly, do not touch anything in `output/`. That's all generated.

What you're looking for is in `posts/:slug/`. That directory contains all the sources for a post, with the post itself being named `post.md` and the rest being images and external files.

## How to edit it?

The general format is:

```
YAML header
---
markdown content
```

Generally you probably shouldn't need to touch the YAML header.

When it comes to the content itself, there are few caveats:

- There must be exactly 1 `h1`-level heading. That's the main post title.
- Directly after there has to be excerpt. Excerpt is a paragraph of text wrapped by `_`.

So the minimal content looks like this:

```md
# Hello world!

_This is the first post that says hello world!_
```

This structure is already there with all my published posts. Your only job is not to break it :smile:

[Format reference](https://github.com/botanicus/blog-generator.js)

## How to test it?

Just enable Travis CI to run on your fork.

Alternatively you can run whatever is in the `script` section of [.travis.yml](https://github.com/botanicus/data.blog/blob/master/.travis.yml).

## And then?

Well, submit a pull request of course!

I promise to seriously consider all the contributions.

Happy coding!
