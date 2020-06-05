# casper

the default theme for [ghost](http://github.com/tryghost/ghost/). this is the latest development version of casper! if you're just looking to download the latest release, head over to the [releases](https://github.com/tryghost/casper/releases) page.

&nbsp;

![screenshot-desktop](https://user-images.githubusercontent.com/353959/66987533-40eae100-f0c1-11e9-822e-cbaf38fb8e3f.png)

&nbsp;

# first time using a ghost theme?

ghost uses a simple templating language called [handlebars](http://handlebarsjs.com/) for its themes.

this theme has lots of code comments to help explain what's going on just by reading the code. once you feel comfortable with how everything works, we also have full [theme api documentation](https://ghost.org/docs/api/handlebars-themes/) which explains every possible handlebars helper and template.

**the main files are:**

- `default.hbs` - the parent template file, which includes your global header/footer
- `index.hbs` - the main template to generate a list of posts, usually the home page
- `post.hbs` - the template used to render individual posts
- `page.hbs` - used for individual pages
- `tag.hbs` - used for tag archives, eg. "all posts tagged with `news`"
- `author.hbs` - used for author archives, eg. "all posts written by jamie"

one neat trick is that you can also create custom one-off templates by adding the slug of a page to a template file. for example:

- `page-about.hbs` - custom template for an `/about/` page
- `tag-news.hbs` - custom template for `/tag/news/` archive
- `author-ali.hbs` - custom template for `/author/ali/` archive


# development

casper styles are compiled using gulp/postcss to polyfill future css spec. you'll need [node](https://nodejs.org/), [yarn](https://yarnpkg.com/) and [gulp](https://gulpjs.com) installed globally. after that, from the theme's root directory:

```bash
# install dependencies
yarn install

# run development server
yarn dev
```

now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

the `zip` gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
# create .zip file
yarn zip
```

# postcss features used

- autoprefixer - don't worry about writing browser prefixes of any kind, it's all done automatically with support for the latest 2 major versions of every browser.
- variables - simple pure css variables
- [color function](https://github.com/postcss/postcss-color-function)


# svg icons

casper uses inline svg icons, included via handlebars partials. you can find all icons inside `/partials/icons`. to use an icon just include the name of the relevant file, eg. to include the svg icon in `/partials/icons/rss.hbs` - use `{{> "icons/rss"}}`.

you can add your own svg icons in the same manner.


# copyright & license

copyright (c) 2013-2019 ghost foundation - released under the [mit license](license).
