---
title: "Building a Portfolio & Dev Blog"
date: 2025-10-12T12:30:00-05:01
draft: false
tags: ["web development", "frontend"]
categories: ["Software Engineering"]
author: "Troy Archer"
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Key principles and strategies for building a personal portfolio and development blog."
canonicalURL: "https://tarcher.dev/posts/building-a-portfolio/"
disableHLJS: false
disableShare: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>"
    alt: "Scalable web architecture diagram"
    caption: "<text>"
    relative: false
    hidden: true
editPost:
    URL: "https://github.com/TroyArcher/tarcher.dev/blob/main/content"
    Text: "Suggest Changes"
    appendFilePath: true
---

# Building a Portfolio & Dev Blog

It is increasingly more common to find developers with personal portfolios (and sometimes, blogs!) to showcase their skills, projects, and experiences.

At this point in my career, I felt like a simple resume wasn't enough to encapsulate all of the hard work that I've put into my craft. I wanted a platform where I could not only display my projects but also share my thoughts on various tech topics.

## Why Build a Portfolio?
As I mentioned, a portfolio serves as a dynamic resume. It allows potential employers or clients to see my work in action. It also provides a space for me to express my personality and passion for technology, which can be difficult to convey through a typical resume or LinkedIn profile.

LinkedIn profiles are essentially just a resume, but with a few more bells and whistles, basically just formatting and the ability
to be tied into a network. This yields some nice benefits, like being able to be found by recruiters, but it doesn't allow them to really get an insight into who you are as a person or developer.

With company culture being one of the most important factors to me when evaluating a potential employer, I wanted to give them a better idea of who I am to see if I would be a good fit because: *why waste time interviewing with a company that I wouldn't be a good fit for in the first place?*

## Why Add a Blog?
Adding a blog to my portfolio was a natural extension of the idea. It provides a platform for me to share my knowledge and experiences as a senior software engineer.

Writing about technical topics helps me solidify my understanding, stay up to date with the latest trends, and also give a deeper insight into who I am as a developer and person.

Through this medium, I am enabled to share and connect with other developers.

While I interact with many different software professionals day to day, I am limited heavily to the scope and domain in which I operate; this does not give me a broad view of the software industry and I feel compelled to expand my skills in order to remain relevant in a rapidly changing industry (shoutout ChatGPT).

Not to mention, it also demonstrates (and let's me grow) my communication skills, which are crucial in any tech role!

## Tech Stack
When I first thought of this project, I had a few ideas in mind:

### Frontend
- [**React**](https://reactjs.org/): React is a powerful library for building UI components. I have used it in previous projects and am relatively comfortable programming with it. I built an entire static site with React for a fintech project I had been wanting to build for a long time.
- [**Next.js**](https://nextjs.org/): Next.js is a React framework that provides server-side rendering and static site generation. It also has built-in support for routing, which makes it easy to create a multi-page application. It really shines with SEO and performance, which aren't exactly what I'm focused on here, but it's nice to have.
- [**Tailwind CSS**](https://tailwindcss.com/): Tailwind is a utility-first CSS framework that allows for rapid UI development. I love how it allows me to create custom designs without writing a lot of custom CSS. It has a solid ecosystem, but felt like overkill for this project.
- [**Hugo**](https://gohugo.io/): Hugo is a static site generator that is incredibly fast and flexible. It has a large community and a wealth of themes and plugins available. It is ultra easy to set up and use, and it allows me to focus on writing content rather than worrying about the technical details of building a website.

In the end, I ended up trying Hugo first because when I looked at how fast it could spin up an implementation, I was sold. I had heard of Hugo a while back, but never really looked into it until now. 

I spent less than an hour getting a basic site up and running... honestly, it was like 15 minutes.

There were ton of great themes to choose from, and I went with PaperMod because I enjoy the clean and minimalist design. It also had a lot of the features I wanted out of the box, like a dark mode toggle, RSS feed, and syntax highlighting for code blocks.

### Backend
- **None**: Since this is a static site, I didn't need a backend.

I seriously considered integrating with a headless CMS (Content Management System) like [Sanity](https://www.sanity.io/) or [ButterCMS](https://buttercms.com), but in the end it was definitely overkill. I think writing markdown files is a simple way to get points across, is super easy to manage, and best of all, free.

### Devops
- **GitHub Pages**: [GitHub Pages](https://pages.github.com/) is a free hosting service for static sites. It integrates seamlessly with GitHub, which makes it easy to deploy my site directly from my repository. I can also use custom domains and HTTPS, which are important for security and professionalism. 
- **Cloudflare Pages**: [Cloudflare Pages](https://pages.cloudflare.com/) is another great option for hosting static sites. It offers a global CDN, which means my site will load quickly no matter where my visitors are located. It also has built-in support for custom domains and HTTPS, and it integrates with GitHub for easy deployment.

Since I bought my domain through Cloudflare, I decided to go with Cloudflare Pages for hosting. My mind was blown when I realized how incredibly simple it was to set up.

I had already purchased my domain, so I set up Cloudflare Pages to integrate with my Github repo, and within minutes I had successfully configured and deployed my site.

IT WAS SO EASY.

It came with built-in HTTPS, a global CDN, and automatic deployments from my GitHub repo. I never expected it to be so simple and fast (and free!). It also comes with various Cloudflare features like DDoS protection, caching, and analytics, which are all nice to have out of the box

I highly recommend Cloudflare Pages for anyone looking to host a static site. It's free, easy to use, and comes with a ton of great features. I think when I look to evaluate future projects and which stacks I want to use, I will seriously consider using Cloudflare for hosting again.

One final win for Cloudflare Pages is the feature in which it automatically creates a preview deployment for each pull request. This is super useful for testing changes before they go live, and it makes collaboration with others much easier.

## Conclusion
Building this portfolio and blog has been... surprisingly fast and simple. Like it actually was too fast and easy... I was expecting much more of a challenge.

The last major side project I built was a fintech app using React, deployed on AWS with S3 + Lambdas, integrated with ButterCMS, and had a Github Action for CI/CD. I designed overkill architecture for a simple static site.

That took me many months to build and get right. Most of the time spent was fighting with the medium clone that I had forked, and integrating with the headless CMS. I have a feeling that I would have saved a lot of time if I had just used Hugo from the start.

Overall, I am super excited with how this came out, and I am looking forward to investigating what limits I can push this stack to. 

More to come soon!