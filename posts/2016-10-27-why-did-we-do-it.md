title: Why did we do it that way?
url: /blog/why-did-we-do-it/
date: 2016-10-27
description: Why did we do it this way?
image: img/question-mark-1872665_1920.jpg
thumbnail: /img/question-mark-1872665_640.jpg
classes:
- feature-figcaption
- feature-figcaption-hidden
- feature-figlink
- feature-fignum
- feature-tablecaption
tags: blog


Have you ever joined a project and ***not*** soon questioned why things are the way they are? Why was *this* language (or framework) chosen over another? Why do we (or don't we) organize things into microservices? Why are errors handled the way they are? What drove the choice of database, or API design, or external service? 

These questions always come up. It's a natural part of understanding a new work environment. It happens every time. And I don't like being in the position of saying "I'm not sure why this was done/used" in the course of fixing something or implementing something new.

<!-- end-of-preview -->

It is just as much an issue for those who have been on a project for any length of time. Why did we make a particular decision six months ago? Not being able to recall *enough* detail about past decisions isn't usually a deal-breaker for moving forward, but it can significantly help provide context and understanding behind the evolution of a project to the current state. That helps make further changes without breaking or un-intentionally invalidating past decisions.

We make decisions all the time. Some are big, some small. Some have big implications, some not. Projects that try to design/plan a lot up front make decisions early (sometimes with extensive documentation) but validate them later. Other projects decide just-in-time and may not document them at all.

I have seen such decisions documented in formal Word documents, Wikis, User stories (as additional details to the story), email, etc. What has been most useful is making sure they are easy to find, easy to add, and reasonably consistent in format.

## A Lean Experiment

If, like me, you are looking for a lean approach to experiment with you might consider the [Architectural Decision Record (ADR)](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions). These are simply text files checked-in to a project's repository with a simple format that can be as sparsely or densely detailed as needed.

As described, ADRs seem to have just enough information: **Context** of the decision, the **Decision** itself (once made), **Status** (proposed, accepted, rejected, superseded, or deprecated), and **Consequences** of the decision. Since there are potentially some relationships between decisions (such as superseding) there is some maintenance effort needed to properly revise past decisions so the worth of that tradeoff should be part of any experiment using them.

In my experience, they are probably just as valuable in making a decision as in documenting for the future. The process of describing the Context helps in framing the decision and writing a the Consequences for a proposal help communicate information not only for approval but for generating additional work items or changes that may result.

A very public example of these that I have seen recently is in the [Arachne Framework](http://arachne-framework.org), a web development framework for [Clojure](http://clojure.org). The project has a dedicated [repository of ADRs](https://github.com/arachne-framework/architecture) since the project itself is composed of multiple repositories. Some of the records already present include:

* [The use of ADRs (how meta!)](https://github.com/arachne-framework/architecture/blob/master/adr-001-use-adrs.md)
* [How configuration is exposed to users](https://github.com/arachne-framework/architecture/blob/master/adr-005-user-facing-config.md)
* [Asset Pipeline for assets that require pre-processing](https://github.com/arachne-framework/architecture/blob/master/adr-011-asset-pipeline.md)
* [How data will be abstracted/modeled](https://github.com/arachne-framework/architecture/blob/master/adr-015-data-abstraction-model.md)

Note that since this is a relatively young open source project (at the time this article was written) many of these ADRs documented proposals. By the time you read this, some of these may be accepted or even superseded.

## Trying It Out

I have been recommending these as an experiment to teams I work with and using these on projects with overall positive results. There is even a handy [command line tool by Nat Pryce](https://github.com/npryce/adr-tools) to help create/manage ADRs. 

So, whether you are a solo developer or a full team and have been considering a simple way to track decisions, consider experimenting with ADRs or something similarly lightweight.

I'd love to hear experience reports or other approaches that have worked for you.
