---
layout:     post
title:      "Platform Engineering? It's just DevOps!"
subtitle:   "Platform engineering is being hyped, is it a replacement for DevOps or SRE?"
description: "Setting up a blog can be a burden so I searched for the easiest way to host my blog as a developer. In this blog I'll explain how I've set up my blog using Hugo including comments and search and have it automatically update every time I make a change."
date:     2022-11-17
author:     "Geert van der Cruijsen"
image: "/img/platform.jpg"
tags:
    - Blog
    - DevOps
    - Platform Engineering
    - SRE
    - CICD
URL: "/2022/11/17/platform-engineering-is-just-devops"
---

The software industry has a reputation butchering great ideas into things that we call the same but in the end are being mis-used completely compared to the initial concepts. Take "Agile". Everyone is working sprints or using Kanban but a lot of companies are far from actual the actual agile concepts. People use Jira so they are Agile. Same goes for DevOps where a lot of traditional operations teams were rebranded to ops so now they do devops 🤷 , Microservices: just cut your monolith into pieces so you get a large distributed monolith which isn't better than the monolith 🤷.

The problem is often that vendors try to help out with certain problems and then companies think they can just buy Agile by using Jira, You can buy DevOps by using Azure DevOps, Github or Gitlab. A lot of software vendors enable you do do these things better but it's far more than just these tools. It's also they way you work, communicate and your internal operating model.

One of the latest hypes is "Platform Engineering". The idea behind it is pretty good (I'll come back to that in a moment) but the term is already broken before most people actually know what it is because vendors who create "platform engineering tools" butcher the term Platform Engineering. Slogans as "DevOps is dead, use Platform Engineering" totally miss the point. It's NOT another rebrand of your operations department after rebranding it to DevOps or SRE. In my humble opinion the only thing that matters is setting up an organizational structure that works best FOR YOUR COMPANY (which is different from all other companies so stop copy pasting things from other companies without thinking what works for you). 

> TLDR: I see DevOps as a way of working that you could implement in several ways. Platform Engineering and SRE are implementations of this.

![Platform Engineering meme](/img/platform-engineering-meme.jpg)

### DevOps, SRE, Platform Engineering?

Since our industry is changing super fast most terms don't have an official description that everyone agrees on. So to at least be talking about the same thing here I'll drop my definitions of DevOps, SRE and Platform engineering here so that you know where I come from comparing them.

### DevOps
DevOps, a term used for quite a while now in our industry. There are a lot of different opinions about what DevOps is. To me it is much more than just putting some devs and operations people together. It's about creating autonomous teams who focus on delivering business value in a better & faster way. It's a combination of People, processes and tools all working together for the goal of delivering a better product faster. 

Autonomy in this is key. Giving a lot of freedom to teams to live the mantra: "You build it, you run it." This means teams should have the capabilities and responsibilty to make decisions themselves on almost everything. The software they build, the cloud infrastructure they run on, the network that connects their components, the database that stores their data..

These autonomous teams have proven to be highly effective but they also come with a burder. Engineers now need to know more from a lot of things instead of only focus on the code they write. SRE and Platform engineering are forms that can help release this burden.

### SRE
SRE, (Site Reliability Engineering) Invented by Google is a way to add extra reliability to software products by having engineering teams who focus mainly on Reliability. This does not mean that they fix issues for DevOps teams but they are truely engineers who have a lot of expertise in creating reliable software products and can help the DevOps team in improving the way their product works from a reliability perspective. 

At Google DevOps teams need to earn the addition of a SRE team for their product by proving their product is delivering enough business value. 

In this definition of SRE, SRE should not be compared to DevOps. It is just a way of implementing DevOps for large organizations releasing some of the burden of creating high reliable software products when products need to scale to the immense scale of a company like Google.

### Platform Engineering
Platform Engineering teams, the newest hype in creating high performing software organizations should be a similar addition to implementing DevOps if you ask me. The core principle is also releasing the burden of the DevOps teams by creating standardized software platforms that autonomous DevOps teams *can* use. This can be all kinds of products like container hosting platforms, firewall & network controlls, API Management, Cloud infrastructure platforms, DevOps tooling platforms, you name it.

What I don't like about the current platform engineering hype is that there is a really large push on platform engineering products who also mainly focus on kubernetes. Platform engineering teams should NOT be about pushing a platform to autonomous DevOps teams but should rather be ran as an internal product team who's product can be used by DevOps teams if they think this would be a great fit for them.

If DevOps teams would decide not to use the platform that should be just fine! The platform engineering team should create a product that actually delivers value to the DevOps teams and not burden them in such a way that might hinder the DevOps team to deliver business value.

### Who needs Platform Engineering?
In current times where we build modern software I think there is a great place for platform engineering. Autonomous DevOps teams have to focus on so many things that require extra expertise and knowledge that it makes it harder and harder to execute. In these cases Platform engineering can be the answer to make the DevOps teams working on a certain value stream focus more on the actual value tream and use services provided by the platform engineering team.

Platform engineering teams can also focus a lot more in getting to know all the details and focus on tuning underlying infrastructure or software where a DevOps team focussing on a business value stream does not have time for. Key thing here is though that they should never become a bottleneck for these DevOps teams.

Some examples I've seen & helped build at companies:

#### Cloud Platforms
Self service cloud platforms where teams can get their own "landing zone" to create cloud infrastructure and deploy their applications in.

#### Container hosting platforms
Everyone uses Kubernetes nowadays.. Kubernetes does have many cool features but lets face it. It's also really hard to maintain & make secure even if you use one of the managed offerings of the major cloud providers. Having this be managed by teams who also have to focus on business value will cost them a lot of effort they could spend on delivering business value.

#### Api management platforms
As a company you want to be sure that integrations with customers or 3rd parties are made in such a way that everything is consistent. A centralized API management platform helps in creating such a place that is the single entrace for your integration partners where DevOps teams can publish their APIs.

#### Firewall and network platforms
Creating a safe boundary around your network is often complex to make secure but still convinient for DevOps teams to use in an autonomous way. Creating a self service solution here can really help in making it possible for DevOps teams to expose their applications to the outside world without waiting for approvals or the networking team executing the changes for the DevOps team.

#### DevOps tooling platforms
Teams need tools to build their software. In large organizations the teams that maintain these tools can become a bottleneck for other teams that actually want to use these tools. Self service enablement for onboarding, settings, offboarding can help reduce the wait for DevOps teams to get things done and can help in getting teams working on the golden path that helps in compliance & security.

#### IAM Platforms
Within a company you want all applications to be able use the same identity for your users so they can use single sign on throughout the different applications. If you make it possible for teams to onboard their own apps to this identity platform.

> If you see some other examples of platform engineering teams let me know in the comments!

### Conclusion
Platform engineering can be a great way to empower your DevOps teams to be more productive. Focus on making golden path implementations easier through self service but leave the responsibility on making choices at the DevOps teams. Internal platforms that are optional are the best way to go. If a team decides not to use it that's fine. It does mean they have to own things like compliance & security themselves but if that is worth it for them it's OK. Run your platform teams as internal products. have a product vision and treat your other internal teams as actual customers. A Platform engineering team should in the end just be another DevOps team that is responsible to build & run the platform as a product.

I think the book "Team Topologies" does a great job in describing relations between teams. DevOps teams should act as "Stream aligned teams". Focussing on a certain business capability. Platform teams should not act as a enabling team but rather just be a platform team that as i just said provides a platform that teams can choose to use. An SRE team could act in the form of "Enabling team" working together.

![Platform Engineering meme](/img/team-topologies.png)

My final conclusion is that all these things are ideas and concepts that *should* help you deliver software & value to your end customers faster and with better quality. Therefore I see all of this as a form of DevOps instead of competing visions.