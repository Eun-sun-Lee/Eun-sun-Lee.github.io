# BLOG GAME FINAL PROJECT
## 1. Start Github page 
- We use **Github pages** which turn **Github Repo** into **Webpage**.
- Because we have to consider many other factors like Server, DB, Package without **Github pages**.
### step (1) Create Repository
- We have to create a repository in Github which is a name of **<username>.github.io.**

*Warning message*

If you make a repository which has incorrect name, you can't use github pages!!!
![create repository](/2.png)
### step (2) Connect Local-Remote Repository to a Remote Repository
- Copy the address of Remote Repository. 
- To copy the address, you need to press the button which is on the right side.
![create repository](/3.png)
- Then, you have to clone the repository by using below commands.
```
git clone https://github.com/Eun-sun-Lee/Eun-sun-Lee.github.io.git
```
![create repository](/4.png)
### step (3) Write an example file which named index.html
```html
<!DOCTYPE html>
<html>
	<head>
		<title>Github Page Test</title>
	</head>
	<body>
		<h2>This is test page.</h2>
		<p>이 페이지가 잘 보인다면 성공!</p>
	</body>
</html>
```
### step(4) git add, git commit, git push
- Use **git add** command -> takes a modified file in your working directory and places the modified version in a staging area.
- Use **git commit -m** command -> takes everything from the staging area and makes a permanent snapshot of the current state of your repository that is associated with a unique identifier.
- Use **git push** command -> publish an upload local changes to a central repository. 
```
git add *
git commit -m "add: index.html"
git push origin main
```

*Warning message: You have to generate **Personal Access Token(PAT)** to continue.*
- You have to generate **Personal Access Token(PAT)** after you decide Note, Expiration, Scope.
![create repository](/5.png)
Then, you use this token like password.
### step(5) check Github page setting
**Repository Settings> Pages**
![create repository](/6.png)
- Click that Url *https://eun-sun-lee.github.io/*
![create repository](/7.png)
- Then, you can see like above screen under the result of **index.html**.

## 2. Add them on Blog
### step (1) start Jekyll 
- Jekyll is a static site generator.
- You can start Jekyll with the next steps.
```
gem install bundler jekyll
jekyll new . --force
bundle exec jekyll serve
```
- After you execute *(bundle exec) jekyll serve*, you can see below screen if you access *https://127.0.0.1:4000*
![create repository](/8.png)
### step (2) Jekyll
- In **_config.yml**, it is consists of Key Value.
- In **_config.yml**, most of the blog characteristics are managed in this file.
![create repository](/9.png)
- You can also change your blog's name, email, and your name in accordance with your style.
- After you change into them, you can upload to your *<username>.github.io* with below commands.
```
git add *
git commit -m "add: index.html"
git push origin main
```
![create repository](/10.png)
### step (3) Upload first post!
- Blog Posts are progressed in **_posts**.
- We can write new files which are form of *YYYY-MM-DD-TITLE.md* under the _posts directory. 
![create repository](/11.png)
- We have to start the file with that form.
```
layout: post
title: "MongoDB 정리"
date: 2021-11-10 20:34:09 +0900
categories: jekyll update
```
- We can write the contents with the **Markdown** form.
![create repository](/12.png)

### step (4) Add Theme
- Jekyll provides various themes.
- We can use template fit for our purpose like blog, curriculum vitae, etc.
- We can search for our themes in *http://jekyllthemes.org/*
![create repository](/13.png)

**plainwhite Theme**
- I chose plainwhite Theme which is suitable for me. 
![plainwhite theme preview](/screenshot.png)
- To apply that theme, you have to follow these steps.

1. You have to receive theme to local repository with *git clone*
![create repository](/14.png)
2. You have to reflect theme files(plainwhite Theme) to local repository.
**You have to consider dependency when you reflect theme files.**
![create repository](/15.png)

## 3. Customize my blog
### step (1) Customizing blog?
- We can customize our blog in accordance with our style.
![Customize my blog](/16.png)

I changed profile photo into mine, and corrected the introduction(name, school).
```
Eunsun Lee
Kookmin University 20203118
```

I uploaded the main page of the blog with my information. 
![Customize my blog](/17.png)

I posted my **introduction, experience, skills and personal info**. And, I also introduced eunsunBlog's **Contens**.

If you press github icon, you can connect to Eun-sun-Lee's github Url.
![Customize my blog](/23.png)
If you press instagram icon, you can connect to Eun-sun-Lee's instagram Url.
![Customize my blog](/24.png)
If you press facebook icon, you can connect to Eun-sun-Lee's facebook Url.
![Customize my blog](/25.png)

### step (2) Reply with Disqus
- First, we have to join *Disqus* and have a setting.
![Customize my blog](/18.png)
**Start>Configure Disqus**
- You have to set your Website Name and enter the Website URL(your URL of the github.io)
![Customize my blog](/19.png)
- Then, in *Comment and Moderation Settings*, you have to mark *Balanced* and press the *Complete Setup* button to complete.
- You have to add that lines in *_config.yml* to reflect Disqus to Blog.
```
comment:
  provider: "disqus"
  disqus:
    shortname: "esssun"
```
- You have to copy the *Universal Code* in disqus homepage.
*Warning message: You have to check **s.src** part whether it contains your Website Name*
![Customize my blog](/20.png)

- You have to add lines(1,2,8,9,22) like that to reflect disqus to post which I want to insert.
- You have to delete annotation(10~13).
```
1 {% if page.comments %}
2 <h2>Comments</h2>
3 <div id="disqus_thread"></div>
4 <script>
5     /**
6     *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
7     *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
8     let PAGE_URL = "{{site.url}}{{page.url}}"
9     let PAGE_IDENTIFIER = "{{page.url}}"
10    var disqus_config = function () {
11    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
12    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
13    };
14    (function() { // DON'T EDIT BELOW THIS LINE
15    var d = document, s = d.createElement('script');
16    s.src = 'https://esssun.disqus.com/embed.js';
17    s.setAttribute('data-timestamp', +new Date());
18    (d.head || d.body).appendChild(s);
19    })();
20</script>
21<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
22{% endif %}
```

- If you designage **comments: True** in post, you will be allowed to comment on disqus.
![Customize my blog](/21.png)
- Then, you can see that screen on your blog post.
![Customize my blog](/22.png)








































# plainwhite

Simplistic jekyll portfolio-style theme for writers.

**Demo**: [samarsault.com](https://samarsault.com)

![plainwhite theme preview](/screenshot.png)

## Installation on Github Pages

Add this line to your site's `_config.yml`:

```yaml
remote_theme: samarsault/plainwhite-jekyll
```

## Installation

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "plainwhite"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: plainwhite
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install plainwhite

## Usage

The "plainwhite" key in \_config.yml is used to customize the theme data.

```yaml
plainwhite:
  name: Adam Denisov
  tagline: Developer. Designer
  date_format: "%b %-d, %Y"

  social_links:
    twitter: samarsault
    github: samarsault
    linkedIn: in/samarsault # format: locale/username
```

**Updating Placeholder Image**

The placeholder portfolio image can be replaced by the desired image by placing it as `assets/portfolio.png` in your jekyll website, or by changing the following line in `_config.yaml`

```yaml
plainwhite:
  portfolio_image:  "assets/portfolio.png" # the path from the base directory of the site to the image to display (no / at the start)
```

To use a different image for dark mode, e.g. with different colors that work better in dark mode, add a `portfolio_image_dark` entry in addition to the `portfolio_image`.

```yaml
plainwhite:
  portfolio_image:      "assets/eunsun.png"
  portfolio_image_dark: "assets/portfolio_dark.png"
```

**Comments (Disqus)**

Comments on posts can be enabled by specifying your disqus_shortname under plainwhite in `_config.yml`. For example,

```yaml
plainwhite:
  disqus_shortname: games
```

**Google Analytics**

It can be enabled by specifying your analytics id under plainwhite in `_config.yml`

```yaml
plainwhite:
  analytics_id: "< YOUR ID >"
```

**Sitemap**

It can be toggled by the following line to under plainwhite in `_config.yml`

```yaml
plainwhite:
  sitemap: true
```

**Excerpts**

Excerpts can be enabled by adding the following line to your `_config.yml`

```yaml
show_excerpts: true
```

**Layouts**

- Home
- Page
- Post

**Navigation**

Navigation can be enabled by adding the following line to your `_config.yml`

```yaml
plainwhite:
  navigation:
    - title: My Work
      url: "/my-work"
    - title: Resume
      url: "/resume"
```

**Mobile**

By default, Plainwhite places the sidebar (logo, name, tagline etc.) above the content on mobile (narrow screens).
To condense it (moving some things to the bottom of the page and making the rest smaller) so it takes up less space, add the following to your `_config.yml`:

```yaml
plainwhite:
  condensed_mobile:
    - home
    - post
    - page
```

This chooses which layouts (types of page) should be condensed on mobile screens. E.g. if you want everything but the landing page to be condensed, remove `home` from the list. This option does not affect rendering on wider screens.

**Dark mode**

Dark mode can be enabled by setting the `dark_mode` flag in your `_config.yml`

The website will check the OS preferred color scheme and set the theme accordingly, the preference will then be saved in a cookie

```yaml
plainwhite:
  dark_mode: true
```

![plainwhite dark theme previe](/dark.png)

**Multiline tagline**

Tagline can be multiline in this way

```yaml
plainwhite:
  tagline: |
  First Line. 

  Second Line. 

  Third Line.
```

**Search-bar**

Search-bar can be enabled by adding the following line to `config.yml`

```yaml
plainwhite:
  search: true
```

Search is powered by [Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search) Jekyll plugin. A `search.json` containing post meta and contents will be generated in site root folder. Plugin JavaScript will then match for posts based on user input. More info and `search.json` customization documentation can be found in plugin repository.

**Base URL**

You can specify a custom base URL (eg. example.com/blog/) by adding the following line to `_config.yaml`. Note that there is no trailing slash on the URL.

```yaml
baseurl: "/blog"
```

**Language**

You can set the `lang` attribute of the `<html>` tag on your pages by changing the following line in `_config.yml`:

```yaml
plainwhite:
  html_lang: "en"
```

[See here for a full list of available language codes](https://www.w3schools.com/tags/ref_country_codes.asp)

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/samarsault/plainwhite-jekyll. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `plainwhite.gemspec` accordingly.

## Donation
If this project help you reduce time to develop, you can give me a cup of coffee :) 

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://paypal.me/thelehhman)

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## More themes

- [Texture](https://github.com/samarsault/texture)
