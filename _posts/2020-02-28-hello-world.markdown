---
layout: post
title:  "Hello World!"
date:   2021-02-28
tags: xdsd
comments: true
shareable: true
author: SelfXdsd
preview: Introducing Self XDSD, the platform for automated management of distributed projects.
image: https://blog.self-xdsd.com/images/home.png
---

Hello there! We are excited to announce that Self XDSD is now live at [https://self-xdsd.com](https://self-xdsd.com).

In this blog post, let us walk you through an introduction and short explanation of what our platform is about.

<figure class="articleimg">
 <img src="{{page.image}}" alt="The Self PM in Action." style="box-shadow: 2px 2px 2px 2px grey;">
 <figcaption>
 Our PMs report new Issues for each TODO they find in the code.
 </figcaption>
</figure>

# What Is It?

Self XDSD is a platform which implements the [XDSD](https://www.xdsd.org/) management principles for distributed projects. XDSD as a concept belongs to its respective creators -- we are simply implementing it. Our vision is that, not long from now, ``XDSD`` will become an acronym as popular as ``CI/CD`` and that there will be many more XDSD implementors besides us. We can't wait to see how things will unfold.

# The Need For Management

There are countless tools which help distributed projects on Github or GitLab do their work in the most efficient way possible. However, we are not aware of any popular tool which actually automates the Project Management part. We are here to complement the palette of tools that any successful project is using, by **bringing automated project management to the table**.

Our PM will take care of the following for you:

* Issue Assignment
* PR Assignment
* Open/close Issues based on "to-do" and "fix-me" code comments.
* Automatic invoicing and payments

# What You Need To Do

It's not much different from how you set up Travis CI or Coveralls, or other similar tools.

Just log into [Self XDSD](https://self-xdsd.com) using your Github or GitLab account (depending on where you develop your project), select the repository and activate it. When you do this, three things will happen:

1. We register your repository as a managed project and assign it to one of our **chatbot PMs**.
2. We use your OAuth Token to invite the PM to the repository, with management permissions.
3. We set up a Webhook inside your repository, which will be used by Github/GitLab to automatically notify the PM of
certain events (open/close Issue, new Comment etc).

After activating your repository, you need to add **contracts** for each of your contributors. If Jane contributes to your project as a developer, you will most likely want to register two contracts for her: one with the ``DEV`` role (so the PM can assign her Issues to work on) and one with the ``REV`` role (so the PM can assign her as a reviewer to Pull Requests).

That's it. From now own, the PM will watch your repository and will assign any Issues to one of the DEV contributors, for fixing. Likewise, Pull Requests will be assigned for review automatically.

# Basic Cycle

1. Someone opens an Issue in your repository.
2. The PM adds it to scope and assigns it to a DEV contributor (the default estimation for any Issue is ``60 minutes``).
3. Contributor provides a Pull Request which gets reviewed and merged.
4. Issue is closed.
5. The PM adds the Issue to the Contributor's **active Invoice**.

Each Monday, the PM automatically pays Invoices which are over **108,00 EUR**. You can also make payments automatically, from the web UI, after an invoice's value exceeds 108 euros.

We use [Stripe](https://stripe.com) to provide payment functionality and our business model is quite simple: for each payment which goes to the contributors, we charge an **8% commission**. We charge the commission **only** for tasks (issues or pull requests) which are closed and invoiced.

# Dry Run, No Card Required

Don't worry, you don't have to use your credit card right from the start. Each project managed by Self XDSD starts off with a Fake Wallet - this wallet allows you to enjoy all the functionality of Self XDSD without spending a dime. Think of it as of a free trial, or dry run.

# Success Story

Self XDSD is already managing the development of a rather big software product: **itself**. We had an early version of the PM chatbot deployed in a staging environment, to help us manage our work. In other words, **Self XDSD literally managed its own development**. Feel free to go through the [self-xdsd/self-core](https://github.com/self-xdsd/self-core) repository (its Issue tracker), to see how it went. Here is an example [Issue](https://github.com/self-xdsd/self-core/issues/897).

# Give It A Spin

This here was just a high-level overview and we know you probably have many questions. Check out the [documentation](https://docs.self-xdsd.com) for more details or join our [Telegram Group](https://t.me/joinchat/FWpjdxscN7kYhADoVtUV0A) and ask your question right there. We invite you to give Self XDSD a try and see how it works - the best way to discover the powers of any product is to use it.

All this being said, we are excited of this new journey and cannot wait to see how our users will benefit from using our platform.
