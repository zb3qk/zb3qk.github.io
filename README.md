# zb3qk.github.io

Zac's Blog. Using the Reverie [Jekyll](https://jekyllrb.com/)-powered theme.

## Development

### Onboarding
1. This assumes youy already have Ruby installed
1. Follow the Jekyll installation instructions [here](https://jekyllrb.com/docs/)

### Local server
1. Execute `bundle exec jekyll serve`
2. Navigate to the localhost port specified in the output

### Metrics
1. [Google Analytics](https://analytics.google.com/analytics/)

## Important files
1. `_config.yml` - contains jekyll environment variables which are used to populate different elements shared by the site as a whole

### Publish a blog post

Create a new file eg. `/_posts/2019-2-13-<your-post>.md` to publish your blog post. That's all you need to do to publish your first blog post! This [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) might come in handy while writing the posts.


## Using Categories

You can categorize your content based on `categories` . For this, you just need to add `categories` in front matter like below:

For adding single category:

```md
categories: JavaScript
```

For adding multiple categories:

```md
categories: [PHP, Laravel]
```

The categorized content can be shown over this URL: <https://zb3qk.github.io/categories/>

## Pagination

Pagination of posts in Reverie works out-of-the-box. You only need to specify the number of posts you want on a single page in `_config.yml` and Reverie will take care of the rest.

```yml
paginate: 6
```

## RSS

Reverie comes with a [RSS feed](https://en.wikipedia.org/wiki/RSS) in-built. The generated RSS Feed of your blog can be found at <https://yourgithubusername.github.io/feed>. You can see the example RSS feed over [here](https://reverie-jekyll.netlify.app/feed.xml).

## Sitemap

The generated sitemap of your blog can be found at <https://zb3qk.github.io/sitemap.xml>. 
