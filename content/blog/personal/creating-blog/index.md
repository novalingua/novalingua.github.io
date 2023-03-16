---
title: "Creating a blog"
summary: How and why I started my own blog, Hugo, and free static site hosting.
description: How and why I started my own blog, Hugo, and free static site hosting.
date: 2023-02-15T01:00:48+07:00
categories:
    - personal
    - tech
cover:
    image: feature.webp
draft: false
---
{{< lead >}}
How and why I started my own blog, static sites, and free hosting.
{{< /lead >}}
## Why a blog at all

I am *always* running into things that I want to learn. Sometimes, I learn things because I have an idea that I want implemented. Other times, I come across something that, frankly, just look fun. This is how I end up with a media server that is auto-updated with new movies and series, a personal music server that lets me listen lossless quality audio on my phone and computer, a Moodle instance that I use to distribute online exercises and tests to my students, my own cloud storage, and, well, this blog.

However, a problem that I constantly have to deal with is that my brain only *really* understands something once I've talked about it or explain it to someone else. And finding a friend to talk about the hottest movies or TV shows is easy, finding somebody to explain what `git` is or discuss the difference between static and dynamic sites is *substantially* more difficult. The average person is simply not that technical, nor do they need to be.

Another problem that has been nagging me is that sometimes when I'm teaching, I may think of a good way to explain a concept or a lesson. I usually write these ideas down into whatever note-taking app that I happen to be using at the time, *but then I rarely revisit them*. Personal notes is not very inductive to sharing - what with them being personal and all - so I hardly ever get the chance to convey these ideas to other people.

And then, I had the bright idea of starting a blog. Not only would this solve both these problems, I've found that writing is sorta therapeutic. It helps me relax and clear my mind.

So, this is how I did it, through (a lot of) trials and errors.

## Content management systems

### Wordpress

![Wordpress](wordpress.webp#center)

When I first had the idea of a blog, the first tool I tried was Wordpress. After all, it is the most popular CMS on the planet, with about 43% of **all websites on the internet** being built on Wordpress. Let that sink in for a moment - almost ***half*** of all the sites on the internet is built using this single tool. That alone should give you an idea about the capabilities and extendability of Wordpress.

Because it's so popular, the community around Wordpress is huge, which means you almost never run into problems that don't have solutions already. The plugin ecosystem is also very extensive and most of the times there will be a plugin that will help you achieve whatever your heart desires.

**But therein lies Wordpress greatest weaknesses**. Because of its popularity, Wordpress sites are a major target for malicious hackers. The third-party plugins on your site means additional code that constantly needs to be updated and to be processed by your web server. This makes a great number of Wordpress sites slow and insecure.

Overall, Wordpress is a powerful tool but for simple blogs, it's slow, bloated, and unnecessarily complex.

### Ghost

![Ghost CMS](ghost.webp#center)

Ghost is another popular CMS. It's fast, simple, and intuitive. If you put a caching layer on top of it, like a CDN for instance, it should be quick enough for most people.

But it's **too** simple. There's only a few themes available for free, and even though they're not bad, I simply didn't like that I had to dive into HTML and CSS files to change its looks - or buy a premade theme.

What's more, the management interface was non-customizable, and Ghost's editor is very limited. It doesn't render Markdown correctly (which I prefer to write in), and it doesn't fully support Vietnamese, the language of many of my posts.

### Other CMS'

I tried a few other popular CMS' too, unfortunately they all eventually run into the same problems - either they're *too complex*, or *too simple*.

Then, I stumbled upon a blog post that mentioned using Ghost as a Headless CMS for a "Gatsby" site.

*My first reaction was "Headless... what now?"*

## Static sites? Sounds good.

So what is a "headless" CMS? It's just a fancy term for "online content editor" but without the actual website, or "frontend". For the actual pages that visitors would see on their browsers, you'd utilize something like Gatsby - a <mark>**static site generator**</mark>.

### Static vs dynamic content

*Warning: lots of technical jargon ahead.*

When you visit a website, there are generally 2 types of content, *static* and *dynamic*.

#### Static

Static content is content that is served to all users in the same manner. Think of images or videos: these assets do not need to be changed or edited often. There are of course other kinds of static content, most notably HTML (content/layout) and CSS (styling) files.

So what are the benefits of static content? For laymen like me, the main benefit of static content is that they don't have to be regenerated every time someone visit my site. Static assets can be cached (stored for a long time for quick retrieval) very efficiently, either locally (in RAM for example) or by using a Conten Delivery Network (CDN) like Cloudfare or BunnyCDN. This is a cheap and effective way to reduce the computing load on my server - less computing load means that I am able to rent less powerful hardware, thus reducing the overall hosting costs. Another big plus is that serving content through cache is **wicked fast**.

#### Dynamic

Dynamic content have to be processed for each visitor individually, and change depending on the web request. These are your shopping carts, your payment information, your data. Anything that changes on user input.

These types of content are immensely powerful, but they are **heavy** on the computer serving the web page, as they have to listen for inputs and use those to calculate and generate outputs. Luckily, what I'm mainly interested in is building a blog, and in my opinion blogs should have *close to no* dynamic content.

### Headless CMS?

So is my best choice a headless CMS with a static frontend then?

The answer (for me personally) is no. After some thinking, I realized that all I needed was a program to edit Markdown files, then use those files to generate static HTML and CSS files, and upload those to some server. So why would I choose to write using an editor that I'm not happy with? There is a plethora of offline Markdown Editors that offer vastly superior editing capabilities and writing experiences, so I don't have to be chained to some functionally-limited online editor.

### Hugo

![Hugo](hugo.jpg#center)

After some research, I chose [Hugo](https://gohugo.io/) as my static site generator, due to its speed and simplicity.

What I like about Hugo:
1. All my content is stored and categorized neatly inside folders. All I need is a text editor to write and edit blog posts.
2. Hugo builds really fast. My site never takes more than 5 seconds to build each time I change something.
3. All the static files Hugo builds is put into 1 folder, that I can then upload to whichever hosting provider I choose.
4. It's really simple to use. I just navigate to the project folder, run `hugo server` to preview my changes, then `hugo` to build it. (I use a Github repository, however)
5. There are many free Hugo themes that I find pleasing enough to use.

## How I do it

### Content management

I use a Github repository to store all my content, and a local version of that repository for editing purposes. This has 2 benefits:
1. Everything is backed up somewhere. I trust Github to not lose my files more than I trust myself.
2. I can easily revert to a previous version if I mess up the code somehow.

For editing, I use [VSCode](https://code.visualstudio.com/). It's fast, and git is integrated, so I don't have to run `git commit`, `git add`, and `git push` every time I change something. For someone with very little experience with coding/programming such as myself, it's just a more user-friendly way to use git. I write in Markdown, so I really don't need or want an editor bloated with toolbars and font styles and whatnot. If you don't like using VSCode and just want an editor focused on writing content, [Obsidian](https://obsidian.md/) is another excellent choice.

### Hosting provider

Static sites like Hugo is extremely lightweight so serving them doesn't take much computing resources at all. Thus, there are many free options out there for hosting static websites: [Github Pages](https://pages.github.com/), [Cloudflare Pages](https://pages.cloudflare.com/), [Netlify](https://www.netlify.com/), [Vercel](https://vercel.com/), [Firebase](https://firebase.google.com/), etc. These often have very generous resource limits for free plans, enough for all but very heavy users. If your static site consistently hits these limits, though, you can probably monetize it somehow, so hosting costs shouldn't be a problem in that case. As an example, Netlify's free tier includes 100GB of bandwidth monthly, and this blog is currently about 40MB in size. To hit Netlify's free tier limit, NEOLINGO would have to be served in its entirety to 2,500 visitors each month, with each visitor clicking on *every single page*. In most cases, the number of monthly visitors would have to be considerably higher to hit this limit, since not everyone would visit all the pages on my site.

Personally, I've tested 3 providers: Netlify, Github Pages, and Cloudflare Pages. After extensive experimentation, I've found that Github Pages is the fastest provider of the three, so that's what I went with. 

In my opinion, though, deploying your site on Netlify or Cloudflare Pages is considerably easier since you don't have to deal with `git` at all, and they are indeed good enough for most people (under 2 seconds to load the whole site), so I'm leaving the instructions here:
1. Register an account with Netlify/Cloudflare
2. Create a Netlify/Cloudflare Pages project
3. Install `netlify-cli`/`wrangler`
4. Create Hugo site, write content, then use `hugo` to build your site (the output is often everything in the `public` folder within your project)
5. Deploy using one of these two commands from your project root folder, depending on the provider you choose:
   - `netlify deploy --prod`, enter `public` when prompted for `Publish directory`, then choose the project you previously created on Netlify
   - `wrangler pages publish --project-name name-of-cloudflare-project ./public`, remember to change `name-of-cloudflare-project`

For deploying on Github Pages, you can follow the official documentation [here](https://gohugo.io/hosting-and-deployment/hosting-on-github/).

## What now?

One thing I don't really like about Hugo is that its themes are a little on the simpler side. I'm currently looking into [Astro](https://astro.build/), but the process is a little bit more technical.

This blog will be updated in the future in case I change my setup.

## Closing thoughts

Hugo is an excellent tool to have a website running really quickly and cheaply. It's blazing fast, too, taking less than 1 second to load even on slow internet.

If you're looking to build a blog, portfolio, or a website in general, it's definitely worth considering.