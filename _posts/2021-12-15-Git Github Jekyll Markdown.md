---
layout: post
title:  "Git Github Jekyll Markdown"
date:   2021-12-15 17:40:41 +0900
categories: jekyll update
comments: true
---

# Git Github Jekyll Markdown
1. **Git&Github**
![photo](/40.png)

**git**
- Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
- Git is easy to learn and has a tiny footprint with lightning fast performance. It outclasses SCM tools like Subversion, CVS, Perforce, and ClearCase with features like cheap local branching, convenient staging areas, and multiple workflows.
- Git is an ** Distributed version control system .**

**Git's branch**
- A branch represents an independent line of development. The git branch command lets you create, list, rename, and delete branches. It doesn't let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the git checkout and git merge commands.

![photo](/31.png)

- A branch represents an independent line of development. Branches serve as an abstraction for the edit/stage/commit process. You can think of them as a way to request a brand new working directory, staging area, and project history. New commits are recorded in the history for the current branch, which results in a fork in the history of the project.
- The git branch command lets you create, list, rename, and delete branches. It doesn’t let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the git checkout and git merge commands.
```
git branch
```

**Github**
- GitHub is a provider of Internet hosting for software development and version control using Git. It offers the distributed version control and source code management (SCM) functionality of Git, plus its own features. It provides access control and several collaboration features such as bug tracking, feature requests, task management, continuous integration and wikis for every project.
- It is commonly used to host open-source projects.

![photo](/41.png)

2. **Jekyll**
- Jekyll is a static site generator. 
- Written in Ruby by Tom Preston-Werner, GitHub's co-founder, it is distributed under the open source MIT license.
- Jekyll is a simple, blog-aware, static site generator perfect for personal, project, or organization sites. Think of it like a file-based CMS, without all the complexity. Jekyll takes your content, renders Markdown and Liquid templates, and spits out a complete, static website ready to be served by Apache, Nginx or another web server. Jekyll is the engine behind GitHub Pages, which you can use to host sites right from your GitHub repositories.
*Gem Version Linux Build Status Windows Build status Security Backers on Open Collective Sponsors on Open Collective*

![photo](/42.png)

**Github pages**
- GitHub Pages is a static site hosting service that takes HTML, CSS, and JavaScript files straight from a repository on GitHub, optionally runs the files through a build process, and publishes a website. You can see examples of GitHub Pages sites in the GitHub Pages examples collection.
- You can host your site on GitHub's github.io domain or your own custom domain. For more information, see "Using a custom domain with GitHub Pages."
- If your project site is published from a private or internal repository owned by an organization using GitHub Enterprise Cloud, you can manage access control for the site. In an enterprise with managed users, all GitHub Pages sites are privately published. For more information, see "Changing the visibility of your GitHub Pages site."
- To get started, see "Creating a GitHub Pages site."
- Organization owners can disable the publication of GitHub Pages sites from the organization's repositories. For more information, see "Managing the publication of GitHub Pages sites for your organization."
```
git clone https://github.com/username/username.github.io
cd username.github.io
echo "Hello World" > index.html
git add --all
git commit -m "Initial commit"
git push -u origin main
```
3. **Markdown**
- Markdown is a lightweight markup language that you can use to add formatting elements to plaintext text documents. Created by John Gruber in 2004, Markdown is now one of the world’s most popular markup languages.
- Using Markdown is different than using a WYSIWYG editor. In an application like Microsoft Word, you click buttons to format words and phrases, and the changes are visible immediately. Markdown isn’t like that. When you create a Markdown-formatted file, you add Markdown syntax to the text to indicate which words and phrases should look different.
- For example, to denote a heading, you add a number sign before it (e.g., # Heading One). Or to make a phrase bold, you add two asterisks before and after it (e.g., **this text is bold**). - - It may take a while to get used to seeing Markdown syntax in your text, especially if you’re accustomed to WYSIWYG applications. The screenshot below shows a Markdown file displayed in the Visual Studio Code text editor.
![photo](/44.png)

1. Create a Markdown file using a text editor or a dedicated Markdown application. The file should have an .md or .markdown extension.
2. Open the Markdown file in a Markdown application.
3. Use the Markdown application to convert the Markdown file to an HTML document.
4. View the HTML file in a web browser or use the Markdown application to convert it to another file format, like PDF.



