# mere-blog-theme

[![Gem Version](https://badge.fury.io/rb/mere-blog-theme.svg)](https://badge.fury.io/rb/mere-blog-theme) 
![Gem](https://img.shields.io/gem/dt/mere-blog-theme)

Mere is a minimal and simple blog theme, and nothing more, for use with Jekyll and GitHub Pages. It has been built with the Bulma frontend framework.

It has a homepage which displays the latest 6 posts and a paginated blog page used to list out all blog posts. 


## Installation

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "mere-blog-theme"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: mere-blog-theme
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install mere-blog-theme

## Usage

* [Blog Setup](#blog-setup)
* [Posts](#posts)
* [Homepage](#homepage)
* [Authors](#authors)
* [Google Analytics](#google-analytics)

### Blog Setup

Create a `blog` directory with an `index.html` file inside it. Set the front matter of the `blog/index.html` page with the layout of blog. 

```yaml
layout: blog
title: Blog
```

Set the paginator up in the `_config.yml` file with the posts per page and the path to the blog.

```yaml
paginate: 5
paginate_path: "/blog/page:num"
```

### Posts

Posts should be created in the _posts directory as per standard Jekyll usage. The frontmatter should contain the layout of post, the image to use in the header and the homepage / blog page, the title of the post and the author of the post. You can also set a subtitle for the post if you want to.

```yaml
layout: post
title: First Post
image: /img/home.jpg
author: C.S. Rhymes
```

Wide images will work best, with a minimum width of 1400px. 

### Homepage

Finally, configure the homepage by creating an `index.html` page and configure the frontmatter with the layout of homepage, the title, subtitle (optional) and the image. You can set the hero_height to is-large if you want to make the homepage header a bit larger. 

```yaml
layout: homepage
title: Mere Blog Theme
subtitle: This is the demo site for the Mere Blog Theme
image: /img/home.jpg
hero_height: is-large
```

### Authors

To enable the authors section, create a directory named `_authors` and create a page for each author within it. The author pages should have front matter in the following format. 

**NOTE** The author name should match the author name in their posts exactly. 

```yaml
layout: author
title: The authors page title
name: Author Name
position: Web Designer
description: The short description of the author
avatar: /img/avatar.png
website: https://www.csrhymes.com
```

The website and avatar are optional, but if you are stuck for author images, why not try [https://getavataaars.com](https://getavataaars.com). Square images work best. You can then write about the author in the page content. 
 
Next, create an `authors.md` page in the root of your site and set the layout to authors.

```yaml
layout: authors
title: Authors
description: The authors page
```

Add authors as a collection in your _config.yml file with output set to true so the pages are generated. 

```yaml
collections:
  authors:
    output: true
```

When you build your site, the authors link will appear in the navbar. The authors page will display the authors you have added. You can then click on their name or image to view the author page, along with a list of their 4 latest posts. 

There will also be a link back to the authors page at the bottom of the post. 

### Google Analytics

To enable Google Analytics add `google_analytics: UA-xxxxxxxx` to your `_config.yml` replacing the UA-xxxxxxxx with your Google Analytics property.

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/chrisrhymes/mere-blog-theme. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `mere-blog-theme.gemspec` accordingly.

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

