---
layout: post
title: Goodbye Wordpress - Hello Jekyll!
date: 2021-04-18
categories: 
    - web dev
    - personal
---


I started using Wordpress when setting up my personal blog back in summer 2017. But increasingly, I wanted a change. This is why I moved to another solution, a personal website built via a static site generator and hosted with Github Pages. In this post, I want to explain in very simple and non-techy terms how I set up this new personal website and why I chose to do so. I mainly do this for personal reference, so I don't forget what I learnt in the process, but it may be also of interest to some readers.

## The Big Picture

It's always good to begin with the end in mind. What is my goal? What am I trying to achieve with my website? And how "techy" do I want to go? 

My website should be my bundled web presence. That is, a place for me to share thoughts and information with the outside world. It should be:
- minimalistic
- inexpensive
- content-focused

To be completely honest, Wordpress.com is still able to do most of what I want. Based on the WYSIWYG (What you see is what you get) principle, design of the website is relatively straightforward. But what I found increasingly annoying about Wordpress after some time was the "bloatedness" of the whole platform. There were a lot of features I never used and one could only write posts online. I prefered having an offline version of my posts first, before publishing them live. 

On the technical side of things, since I am not a web developer, I prefer using a solution that I can easily handle myself. I am okay with spending some time on the set-up of the site, if after that the maintenance costs are very low.

## The Solution: Github Pages and SSG

There seems to be a spectrum of:
High degree of technical complexity + very flexible and customizable **vs.** low degree of technical complexity ("drag and drop", WYSIWYG) + inflexible and pre-made designs.

While Wordpress is on the latter part of the spectrum, I wanted to move further to the former. 

I considered Ghost, an open source blogging platform which claims to be a "fast, modern WordPress alternative". But it seemed rather expensive and at its core not *that* much different to Wordpress.

In the end, I settled for the free and flexible solution of building my site with the static site generator Jekyll and hosting it via Github Pages.


### Introduction to Static Site Generators

Jekyll is an open source static site generator. What is a static site generator, or SSG for short? Let's first look at the "site generator" part of it. In simple terms, an SSG is just like a function. It takes input (markdown files as content, templates) and generates output (html files, ready-to-show web pages). These html files can then be uploaded to a serve and be viewed in a browser.

The "static" part means that there is no database behind the content. Whereas Wordpress manages content in a database and retrieves the relevant piece of content when it is requested, the SSG generates html pages in advance in a build process. A SSG, as the name suggests, only works for static sites. Dynamic sites on the other hand are in a constant state of change (think Twitter, Youtube etc.). Therefore, for dynamic sites a database is necessary because the displayed content always changes.

For a personal website however, where the content rarely changes and only when I choose to upload something new, a SSG is a good choice. This is then what happens:

1. I create a static site that consists mainly of html pages
2. I take the static site created by SSG and deploy it to the server
3. When a user requests a page, the server finds the matching file and send it to the user, who sees it displayed in their browser

#### Benefits of SSG

1. Reducing site complexity
2. No need to manage databases and therefore higher security
3. Low to no cost for support and maintenance

One disadvantage of SSG is that it requires a few more technical skills. After all, tools like Wordpress are so great because they are so user-friendly and effortless to use. You just drag and drop your components of your website. This is not the case for SSG. 

#### Types of SSG

There are many different SSG out there, due to their growing popularity over the last couple of years. Jekyll, Gatsby, Hugo, Eleventy ... you name it! 

### How does Jekyll work?

I chose Jekyll because it has good documentation and is tightly integrated with Github Pages, where I was planning to host my website.

Jekyll is written using the language Ruby. A Ruby gem is a package of Ruby code that you can download and install. Gems have specific functionality and can perform actions. For example, *Bundler* is a gem that installs all gems in a *Gemfile*. A *Gemfile* include the list of gems used by the site. When using a Gemfile, you can use the following command to build your site:

```
bundle exec jekyll serve
```

Jekyll has built-in support for Github Pages.


### Github Pages

Github Pages is a hosting service for static sites. It takes the files from a github repository and publishes a website. In some sense, it is just acting as a web server. The great thing about it: It's free! The site with a github.io domain is automatically generated by Github Pages when pushing the source files. In concrete terms, this means: I write a new blog post, like this one, commit to the Github repository that is being used to host my website and then the website will be automatically built to publish the new article. Like magic!

#### Themes in Github Pages

This is where it gets *creative*. 

I wanted a theme with a visible side/navigation bar. I considered Poole and Hyde, but both of them were a little too plain for me. 

[Hydejack](https://hydejack.com/) is a theme that fulfils the side bar requirement AND looks elegant on top of that. It also has a decent manual for beginners. To get the theme running, I installed the theme via bundler by adding the respective gem to my gemfile and by setting the remote-theme to "hydecorp/hydejack". 

**How I customized the Hydejack theme to my needs:**

Starting off, I did the following:
- spent time to understand the jekyll folder structure, that posts are saved in the _posts folder, that the config.yml file is the central file for settings and that I needed to create _pages and assets folders for my other data 
- edited the config.yml file with my custom information
- created menu bar for "About", "Blog" and "Resume" Pages

The next step was to add the content and to prettify the site. For this, I :
- migrated old posts from Wordpress to the new site, individually went through each post to make sure the images were displaying and the links were working
- set up the blog post to display in a list format all posts sorted by year
- added an embedded resume pdf
- added social media icon links
- added new sidebar image

### Buying a domain and linking to Github Pages

The final step was to use a custom domain instead of the github domain "celineli99.github.io". I went over to namecheap.com, selected the one I liked (luckily celineli.com was still free) and linked it to my github address as per [this tutorial](https://dev.to/pauljwil/connect-github-pages-to-your-namecheap-domain-4gjj). Voilà!

---

That was, in simple terms, the process of how I set up this website. Overall, I am happy with the result and with what I learnt. Of course, there is much more I could do but I am already satisfied with the current set-up. So I think I will use this as a starting point for the future, and make smaller adjustments along the way as needed.

If you have any tips, improvement suggestions or other feedback please let me know! Thank you for reading!