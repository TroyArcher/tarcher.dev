---
title: "Building a Hackathon Project"
date: 2026-02-28T12:30:00-05:00
draft: false
tags: ["backend", "ai"]
categories: ["Software Engineering"]
author: "Troy Archer"
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Hackathons are a fantastic way to level up and learn new skills. Let's dive in to the process of building a hackathon project, from ideation to execution."
canonicalURL: "https://tarcher.dev/posts/building-a-hackathon/"
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

# Building a Hackathon Project

Hackathons are a fantastic way to level up and learn new skills. They provide an opportunity to work on exciting projects, collaborate with others, and push your limits in a short amount of time. I'm extremely thankful that [Bandwidth](https://www.bandwidth.com/) has just finished hosting our second annual hackathon. We made many improvements over last year, both in the event itself and in the projects that were built. 

## Planning

Just a quick note before we dive into the projects: as a part of the Hackathon's planning committee, I had the opportunity to directly impact the event itself. It was great being able to see how these events get put together from behind the scenes and how many great people we have at Bandwidth that are passionate about making these events successful.

We met weekly for about 3 months leading up to the event to plan and execute on the various aspects of the hackathon, including: timing, food, crowdsourcing project ideas, judging criteria, feedback from last year's event, and constant updates going out to the organization. We ended up with a great event that was focused on AI and how we as a business can use it to supercharge our products and services to better serve our customers.

Shoutout to the rest of the team, I was just a small part of a much larger effort to make this event a success, they were the real heroes! (I didn't obtain permission to link them here, but you know who you are!)

## Last Year's Project

Last year was the first Hackathon at Bandwidth. I partnered with four of the best engineers I've had the pleasure of working with here, and we built a project called Handbrake. Handbrake was a tool that used AI to evaluate message content and compare it against the intended use case of the Toll-Free Verification. 

### The Problem

In the world of messaging, there are various use cases for which businesses can use messaging to communicate with their customers. These use cases include things like appointment reminders, two-factor authentication, marketing campaigns, and more. Each of these use cases has different requirements and restrictions around them, and it's important for businesses to ensure that they are using messaging in a way that is compliant with these requirements.

We have many different channels (like 10 digit long-codes, toll-free numbers, short codes, alphanumeric sender IDs, RCS for Business, etc.) that are used for different use cases and sending rates. Since the team had specific expertise with Toll-Free Verification, we decided to get laser focused on that channel for our project. Toll-Free Verification is a service that allows businesses to register their toll-free numbers with Bandwidth and specify the use case for which they will be using messaging. This allows us to verify who is sending these messages and why they are sending them.

If a business is sending messages that are for a given use-case that matches their verification, then everything is fine. However, if they start sending other messages that have nothing to do with that use-case, they can get into trouble with carriers and regulators, which can lead to fines and even losing the ability to send messages altogether. They would need another number and verification to be able to send these other messages. This traffic also reflects on Bandwidth's reputation in the industry with carriers and other partners.

### The Solution

When you're sending billions of messages a year, it's not feasible to have support staff evaluating these messages manually. We built a system that is both compliant and effective at evaluating message content and comparing it against the intended use case of the Toll-Free Verification. We used a combination of AI and rule-based systems to evaluate the messages and determine if they were compliant with the intended use case.

We used synthetic data to train our AI models, which allowed us to create a system that could effectively assign confidence scores to it's assumption of whether or not messages were compliant with the intended use case. The application itself was quite simple, it was a simple API that accepted a use case, use case summary, and message content. The JSON body returned was a confidence score and reasoning for why the system thought the message was or was not compliant with the intended use case. This allows staff to block messages that are non-compliant and reach out to customers to ensure they are following the rules and regulations around messaging.

If you'd like to read more about last year's project, check out the blog post I wrote about it here: [Hackathon 2025](https://tarcher.dev/posts/hackathon-2025/).

## This Year's Project

This year, we 