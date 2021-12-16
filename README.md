# BLOG GAME FINAL PROJECT
![create repository](/30.png)
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