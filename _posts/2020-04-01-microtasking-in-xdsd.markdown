---
layout: post
title:  "Microtasking In XDSD"
date:   2021-04-01
tags: xdsd
comments: true
shareable: true
author: SelfXdsd
preview: Introducing Self XDSD, the platform for automated management of distributed projects.
image: https://blog.self-xdsd.com/images/home.png
---

The automation that Self XDSD provides is largely owed to a concept called **microtasking** or, in the terms introduced by
XDSD, **Puzzle Driven Development** ([XDSD whitepaper](https://www.xdsd.org/XDSD-WhitePaper.pdf)). Although these terms may
sound strange at first, you may have heard of the [Pomodoro Technique](https://en.wikipedia.org/wiki/Pomodoro_Technique) - they are almost
synonyms.

Let's see how microtasking works in Self XDSD.

<figure class="articleimg">
 <img src="{{page.image}}" alt="The Self PM in Action." style="box-shadow: 2px 2px 2px 2px grey;">
 <figcaption>
 Our PMs report new Issues for each TODO they find in the code.
 </figcaption>
</figure>

# Breaking The Scope

One of the toughest jobs of a Project Manager is breaking the scope of work into smaller pieces. This gets even harder if the Project Manager has no
technical knowledge. Even worse, very few Project Managers in IT actually have any coding knowledge.

So, how can a chatbot do it? The answer is: they cannot do it either - well, unless we're talking about some advanced AI which is not yet available on the market.

# The Answer

Since the Project Manager is not the right person or program to do the job, the only logical answer is: the developers are the ones who should break their work or tasks
into smaller pieces.

How is this achieved by Self XDSD? By having **fixed estimations**. The PM chatbot always estimates any Issue at ``60 minutes`` and that's exactly how much the assignee will be paid when the ticket is closed. Naturally, nobody wants to work more than they are being paid so the first thing the developer has to do is
trim the work that they have to do.

# In practice

How does the developer "trim" their work? By the use of a highly underestimated tool: code ``TODO``s. For example, if the team is practicing ``Test Driven Development``,
the first thing the developer needs to do is to write a few unit tests. Within 60 minutes they can and should write these tests and write a ``TODO`` (or more) in the code, to
delegate the rest of the work. Something like this:

{% highlight java %}
/**
 * Unit tests for {@link AmazonSqs}.
 * @todo #123:60min We wrote the unit tests for connecting and closing
 *  the AmazonSqs instance. Now it's time to provide implementations
 *  for these two methods.
 */
public class AmazonSqsTestCase {

  @Test
  public void canConnect() {
    ...
  }

  @Test
  public void canClose() {
    ...
  }

}
{% endhighlight %}

When the developer pushes this code to the main repository, our chatbot will scan it and it will report a new Issue with the same estimation of 60 minutes and will look for
another assignee for the newly created task. This cycle should be repeated until the whole software module is finally implemented.

Developers can specify the estimation of the ``TODO``s they add. The minimum estimation is 15 minutes, while the maximum is 6 hours. This mechanism exists in order to
accommodate new joiners (new developers on the team), for whom 60 minutes may be too little time to do anything. Once everyone is comfortable, we recommend to always go with the ``60 minutes`` estimation.

Finally, the software module is build like a puzzle, with all these small contributions acting as its pieces, hence the name ``Puzzle Driven Development``.

# Can It Really Work?

We built Self XDSD by following the XDSD methodology ourselves. Actually, we had a very early version of the chatbot PM which helped us (we can safely say that Self XDSD has successfully managed its own development).

We found that developers who were on the team from the beginning were quite comfortable with microtasking, since they knew the codebase from the start. We had a few problems here and there mainly because they were providing Pull Requests which were too big (we recommend that PRs be no bigger than 5 changed files, including tests), but other than that everything went smoothly.

On the other hand, developers who joined the project later in its development were quite shocked. Their job was tougher because they had to learn the project and also get accustomed with the idea of microtasking. We solved this problem by providing a higher estimation (usually 2-3 hours) for their tickets. In general, we believe that anyone with at least one year of coding experience can do something valuable in 3 hours (and delegate the rest), no matter the project.

# Wrapping Up

To wrap up, we hope that we provided a good explanation and overview of what is Microtasking. Feel free to go through [our documentation on the subject](https://docs.self-xdsd.com/microtasking.html) which is more concise and provides another real-life example from our own codebase.

If you have any questions, don't hesitate to ask them in the comments bellow or join our [Telegram Group](https://t.me/joinchat/FWpjdxscN7kYhADoVtUV0A) and ask someone there.
