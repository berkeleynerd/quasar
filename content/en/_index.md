
---
title: "Introduction"
linkTitle: "Introduction"
type: "docs"
tags: ["intro"]
weight: 20

cascade:
- _target:
    path: "/blog/**"
  type: "blog"
  # set to false to include a blog section in the section nav along with docs
  toc_root: false
- _target:
    path: "/**"
    kind: "page"
  type: "docs"
- _target:
    path: "/**"
    kind: "section"
  type: "docs"
- _target:
    path: "/**"
    kind: "section"
  type: "home"
---

{{% pageinfo %}}
a gentle introduction to development using quasar's domain service patterns and tooling
{{% /pageinfo %}}

EVE's thoroughly modern domain service architecture is now feature complete so there has never been a better time to [transcend the monolith](https://wiki.ccpgames.com/display/\~kristinn/2017/07/04/Life+Outside+of+the+Monolith) and help make the dream of [EVE Forever](https://wiki.ccpgames.com/display/CCP/2020/06/15/CEOBlog2020w24+-+EVE+Forever) a reality.

From the perspective of even a seasoned EVE developer, however, there are _**a lot**_ of new technologies and concepts you need to be familiar with to effectively contribute to this effort. Furthermore, it's hard to know exactly where to start on this journey and how to stay on the optimal path through the multitude of confluence pages, READMEs, FAQs, blog posts, and third-party documentation you encounter along the way.

In this guide we attempt to provide just such a starting point for developers new to CCP's domain service architecture and its long list of technologies. Our goal is to help you navigate step-by-step past each technological challenge, summarize the essential knowledge you need to keep going, and point out important internal and external resources you will want to circle back to later once you are well on your way to delivering real business and gameplay value for both CCP and its players alike.

## Setting expectations

Like many other teams at CCP, TechCo maintains an official [working agreement](https://wiki.ccpgames.com/display/TECHCO/Working+agreement+with+teams+collaborating+with+Team+Tech-Co) designed to facilitate a positive and productive working relationship between its staff and other developers throughout the company. **This is an important document** and you should read it in its entirety and bookmark it to refer to later. In fact, many of the topics we will consider in this guide are sourced directly from the working agreement and expanded on to add clarity, detail, and substance.

## Where to find help

If you have questions or run into issues while following along with this guide feel free to ask us for help on Slack. Google and Stack Overflow are surprisingly good resources, as always, but sometimes miss the mark ... when this happens we are here to help!

* For questions about the Go language, tooling, and ecosystem in general reach out for help in the [#golang](https://ccpgames.slack.com/messages/golang/) channel.
* For questions about how to design amazing, bullet-proof protobuf definitions ask for a review in the [#eve-proto](https://ccpgames.slack.com/messages/eve-proto/) channel.
* For all other questions either drop by our desks or chat with us in the [#eve-services](https://ccpgames.slack.com/messages/eve-services/) channel.
* If you run into a blocker you can ping our help desk at **@ttc-help** - whoever is on-call should be able to answer your question or put you in touch with the right resource to help get your issue resolved.

{% hint style="info" %}
Roman's excellent [Eve Service FAQ](https://wiki.ccpgames.com/pages/viewpage.action?pageId=160078718) is an absolutely essential read. Once you are ready to develop a service it will be an indispensable resource!
{% endhint %}

## A look ahead

We use _**Go**_ to write code and tests, _**Git**_ to handle version control, and _**Test Driven Design**_ as our overarching methodology. Combined with judicious use of the _**command line**_ this suite of technologies has allowed us to rapidly and reliably deliver new features while staying "in the flow."

In the next few sections we briefly introduce you to each of these technologies after which we provide a comprehensive tutorial to help you learn _just enough_ of each to kick start your development efforts. After completing this tutorial you will also be better prepared to tackle more advanced Go language learning [resources](https://www.gopl.io).
