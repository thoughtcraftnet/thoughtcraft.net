# Thoughtcraft Website

This is the repo for [thoughtcraft.net][thoughtcraft].  The content is written in [Markdown][markdown] and rendered to static HTML using [Hugo][hugo_site].

## Set Up

    # clone project and submodule
    git clone --recurse-submodules git@github.com:thoughtcraftnet/thoughtcraft.net.git
    

    # if the submodule was missed with the initial clone
    git submodule update --init --recursive


Run the server from within the project root:

    hugo server -D

This starts up a Hugo server listening on http://localhost:1313/

> The `-D` flag is optional and tells Hugo to include pages marked as "draft" status.


## A Note on Front Matter and Drafts

Each content page starts with a section called _[front matter][front_matter]_.  This is easily identified at the top of the file within a section fenced by `---` or `+++`.

The front matter serves as a place to record metadata for the page such as author, background image, keyword tags, and more.  Most fields are self explanatory.

Front matter is also the place where a page is marked as a _draft_.  This is notable because Hugo does not publish pages marked as *draft* to the website.

You can override this behavior in your local installation by running `hugo` with the `-D` flag.  This is useful when authoring content that is not quite ready to be published but you want to check the rendered result.

Example front matter:

```
---
# comments starting with '#' are allowed in front matter
title: "An Awesome Tech Trick I Learned"
date:  2021-10-08
# page is marked as a draft and will not publish to the live site
draft: true
---
```

When you are ready to publish the page, update the value `draft: false`, or delete the `draft` attribute line.

> The `draft` attribute is the first thing to check if a page isn't showing up on the website that you expect.




[thoughtcraft]: https://thoughtcraft.net
[markdown]: https://guides.github.com/features/mastering-markdown/
[git_submodules]: https://blog.github.com/2016-02-01-working-with-submodules/#joining-a-project-using-submodules
[hugo_site]: https://gohugo.io/
[hugo_install]: https://gohugo.io/getting-started/installing/
[front_matter]: https://gohugo.io/content-management/front-matter/

