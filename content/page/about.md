---
title: About
description: About NEOLINGO
date: '2023-02-01'
showtoc: false
aliases:
  - about-us
  - about-hugo
  - contact
menu:
    main: 
        weight: 60
        params:
            icon: user
---

# Welcome to NEOLINGO, a blog about language learning.

This blog will mainly contain methods, tools, and resources for language acquisition, with the occasional personal blog post here and there. The language I'm teaching is English, but hopefully learners of other languages can find something useful here, too.

## Why a blog

I'm an English teacher/tutor, and I find myself wanting a permanent place to store and present my ideas.

My first blog was created with Ghost CMS, which was an excellent option. I hosted NEOLINGO on a VPS I rented and used BunnyCDN for caching. It was acceptably fast and optimized.

However, I had 2 problems with this setup

1. The writing process on Ghost was only okay-ish, since I had to use their web interface to write and publish posts. Instead, I wanted a way to write and edit posts offline, using whatever writing tool I prefer. It's faster, more convenient, and my workflow can be customized to my liking. 
2. Hosting costs. I had to rent a Virtual Private Server in the cloud, since Ghost CMS doesn't play nice with shared hosting. Renting regional servers in Asia was more costly compared to servers in NA or EU, but servers in those regions are far away and thus performance suffers. This necessitated the use of a caching layer, for which I chose BunnyCDN, but that costs money too.

Enter static site generators. Static sites are blazing fast and extremely lightweight, which makes the reading experience more enjoyable. More importantly, static site hosting is cheap or even free - since they're so lightweight, which reduces my hosting costs. This blog is written in VSCode, built using Hugo, and deployed via Netlify/Vercel/Github Pages. All of these tools are free (for now), and writing in Obsidian is **far** better than writing in Ghost editor.

You can learn more about this process [here](https://neolingo.net/blog/personal/creating-blog/)
