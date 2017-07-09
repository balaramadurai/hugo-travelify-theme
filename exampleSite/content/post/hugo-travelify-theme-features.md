---
title: "Hugo Travelify Theme Features"
date: "2016-06-28T13:07:31+02:00"
tags: ["ipsum"]
categories: ["lorem"]
menu: ""
---



**Hugo-Travelify-Theme** is the Hugo version of the Wordpress theme - Travelify . The source code was adapted from *digitalcraftsman*'s Icarus theme with a few changes for additional features (Even this README is a fork from his original theme README :)).

<!--more-->

Some of the important features of Hugo-Travelify-Theme are: 

- Automatic slider generation with banner images

- i10n data

- Disqus integration

- Social media share

- Google Analytics

  ![](/screenshot-1.png)



![](/screenshot-2.png)

![](/screenshot-3.png)

## Get the theme

If you have `git` installed, you can do the following at the command-line-interface at the Hugo directory/folder:

    $ cd themes
    $ git clone https://github.com/balaramadurai/hugo-travelify-theme.git

You should see a folder called `hugo-travelify-theme` inside the `themes` directory that we created a few moments ago. For more information read the official [setup guide](https://gohugo.io/overview/installing/) of Hugo.


## Setup

In the next step navigate to the `exampleSite` folder at `themes/hugo-travelify-theme/exampleSite/`. Its structure should look similar to this:

    exampleSite
    |   config.toml
    +---content
    |   |   about.md
    |   |   contact.md
    |   \---post
    |           creating-a-new-theme.md
    |           go-is-for-lovers.md
    |           hugo-is-for-lovers.md
    |           linked-post.md
    |           migrate-from-jekyll.md
    |           this-post-has-no-body.md
    +---data
    |       l10n.toml
    \---static
        |   new-york-featured.jpg
        \---banners
                7148951717_9bbf185db3_h-1018x460.jpg
                featured-4.jpg
                featured-5.jpg
                new-york-featured.jpg
                placeholder.png
                Spain-Plaza-de-Cibeles-Madrid-1018x460.jpg
                Spain-Plaza-de-Cibeles-Madrid-670x300.jpg
                spain6-1018x460.jpg

In order to get your site running, you need to copy `config.toml` and `data/l10n.toml` into the root folders. (Please refer to http://gohugo.io/overview/quickstart/ for installing a theme)


## The config file

Now, let us take a look into the `config.toml`. Feel free to play around with the settings.

### Automatic Slider

The slider can be switched on and off at will and you can customize the number of banner images you want on the carousel using the parameters in the config.

```
[params.slider]
enable = true
num_features = 4 # The slider picks up the banner images from the N most recent posts, where num_features is N.
```

*Tip* - For best results in the slider, use **1018x460** resolution for the banner images

### Google Analytics

```
GoogleAnalytics = ""
```

### Comments

The optional comment system is powered by Disqus. Enter your shortname to enable the comment section under your posts.

    disqusShortname = ""

Tip: you can disable the comment section for a single page in its frontmatter:

```toml
+++
disable_comments = true
+++
```


### Menu

You can also define the items menu entries as you like. First, let us link a post that you've written. We can do this in the frontmatter of the post's content file by setting `menu` to `main`.

    +++
    menu = "main"
    +++

Furthermore, we can add entries that don't link to posts. Back in the `config.toml` you'll find a section for the menus:

    [[menu.main]]
        name  = "Contact"
        url   = "/contact/"
        weight = 20

Define a label and enter the URL to resource you want to link. With `before` you can decide whether the link should appear before **or** after all linked posts in the menu. Therefore, `Home` appears before the linked post.


### Sidebars

In order to use the full width of the website you can disable the profile on the left and / or the widgets on the right for a single page in the frontmatter:

```toml
+++
disable_profile = true
disable_widgets = true
+++
```

### Tell me who you are

This theme also provides a profile section on the left. Add your social network accounts to the profile section on the left by entering your username under `social`. The links to your account will be create automatically.


### Widgets

Beside the profile section you can add widgets on the right sidebar. The following widgets are available:

- recent articles
- category list
- tag list
- tag cloud
- Duckduckgo search enabled on your website

You can deactivate them under `params.widgets`:

    # Enable and disable widgets for the right sidebar
    [params.widgets]
        recent_articles = true
        categories = true
        tags = true
        tag_cloud = true
        archives = false # This feature is yet to be implemented because of limitations in Hugo's way of working.
        search = true

### Date line

The date line includes: post date, categories, comments and sharing links. However, if you want certain pages to omit the date line, simply put `nodateline = true` in the front matter for that page.

### Disable Previous / next article links and remove tags

To disable the inclusion of a previous/next article link at the bottom of the page, add `noprevnext = true` to the front matter.  Along with this feature, along with `nodateline = true` can be used to create standalone pages that are less "blog-like".

## Localization (l10n)

You don't blog in English and you want to translate the theme into your native locale? No problem. Take a look in the `data` folder and you'll find a file `l10n.toml` that we've copied at the beginning. It contains all strings related to the theme. Just replace the original strings with your own.


## Linking thumbnails

After creating a new post you can define a banner by entering the relative path to the image.

    banner = "banners/placeholder.png"
This way you can store them either next to the content file or in the `static` folder.

*Tip* - For best results in the slider, use **1018x460** resolution for the banner images


## Nearly finished

In order to see your site in action, run Hugo's built-in local server.

    $ hugo server

Now enter [`localhost:1313`](http://localhost:1313) in the address bar of your browser.


## Contributing

Have you found a bug or got an idea for a new feature? Feel free to use the [issue tracker](//github.com/balaramadurai/hugo-travelify-theme/issues) to let me know. Or make directly a [pull request](//github.com/digitalcraftsman/hugo-travelify-theme/pulls).

## License

This theme is released under the MIT license. For more information read the [license](https://github.com/balaramadurai/hugo-travelify-theme/blob/master/LICENSE.md).

## Acknowledgements

Thanks to 

- [Aigars Silkalns](//colorlib.com/travelify/) for creating this theme
- [Steve Francia](//github.com/spf13) for creating Hugo and the awesome community around the project
- [digitalcraftsman](https://github.com/digitalcraftsman) for creating the source code for Icarus theme

