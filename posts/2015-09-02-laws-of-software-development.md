title: The Laws of Software Development
description: What laws, theory's, conjectures describe the fundamental nature of software development?
date: 2015-09-02
image: /img/Laws.jpg
tags: programming,theory,project-management,agile
classes:
- feature-figcaption
- feature-figcaption-hidden
- feature-figlink
- feature-fignum
- feature-tablecaption
- feature-math

I don't *exactly* remember the first time I encountered a *Law*. No, not one of the type intended to govern societal behavior. I'm referring to *Laws* like those that relate to something like physics, mathematics, nature, social sciences, etc. It was probably in a class or in a textbook in my youth and most likely was the ["law of gravity"](https://en.wikipedia.org/wiki/Gravity) or joking references to [Murphy's Law](https://en.wikipedia.org/wiki/Murphy%27s_law).  Wikipedia defines this type of Law as:

> a universal principle that describes the fundamental nature of something, the universal properties and the relationships between things, or a description that purports to explain these principles and relationships.[^law]

One of the core problems in software development, I believe, is remembering and applying the lessons of the past. With the pace of change, experimentation, career path trends, and background diversity of new developers we are challenged to keep up with the knowledge and wisdom that has come before us. Many formal mentoring/apprenticeship programs are highly focused on practical, hands-on application. How do we leverage the wisdom of those who have come before us?

We encounter principles all the time in books, talks, classes, web sites, etc. I have used them in training, printed works, and to help guide me on how to approach certain problems. They sound authoritative, and with good reason: they have stood the test of time (in most cases). In some cases there has been testing and verification, while others are assumed. Whether they are truly *conjecture*, *hypothesis*, *theory*, or *law* is sometimes debateable, still they are principles that are held highly. 

So as someone engaged in gathering people and technology together to deliver products and services I think it is valuable to occasionally reflect on the Laws that relate to Software. How could this be valuable you ask? While some of these may remain without thorough validation, they help guide and shape the thought of our industry. They only serve to help achieve shared understanding of the *fundamental nature* of software if we remember and apply them.

With Software, there are some different areas to consider. Let's not only look at the technical side of things, but those areas involved with conceiving of ideas, collaboration, and execution from the people that make things happen.

## Projects, Plans, and Organizations

Software doesn't write itself, at least not *yet*. 

### Conway's Law ###

>"organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations""
>
>—M. Conway[^conway]

This law is often referenced in the agile community and was named as one of the contributing laws to the Scrum framework in particular. With it we consider how organization of people, approval, hierarchy, etc. affects the design and architecture of the software systems we build. 

Conway's law can be found applied in various contexts:

* Management (product and people)
* Systems design and architecture

### Little's Law ###

Little's Law concerns predictability. MIT professor Dr. John Little describes the relationship between average Arrival (or Departure/Throughput) rate, the average time in the system (Lead Time), and the average # of items in the system (Work In Progress):

>The long-term average number of customers in a stable system L is equal to the long-term average effective arrival rate, λ, multiplied by the (Palm‑)average time a customer spends in the system, W; or expressed algebraically: \\[{L} = {λ}{W} \\]

More commonly in Kanban this is adapted as follows:

\\[{Avg Lead Time}={ {Avg WIP} \over {Avg Throughput}} \\]

An often overlooked aspect of Little's Law is that in order to hold true, certain assumptions must also hold true:

* All three components must be measures in the same item units
* All items that are started must eventually be completed (exit the system)
* The average Arrival and Departure rate need to be balanced (a true pull system)
* The average amount of WIP (W) should be constant/stable
* The average age of items in the system should be stable (not increasing or decreasing)

Focusing on holding to these assumptions allows Little's Law to hold true and allows greater predictability from the system. Understanding the relationships helps understand how to make good decisions regarding each. In Kanban alone practitioners are often advised to focus on these assumptions to guide their policies and actions and use the underlying formulas for understanding how things are related rather than direct calculation.

Little's law can be found applied in various contexts:

* Identifying bottlenecks imposed by testing approaches
* Kanban systems (more common to see an adjusted version of this law focused on Departure Rate (Throughput))
* Hospital emergency department staffing

### Parkinson's Law

Parkinson's Law is usually stated as the adage:

> Work expands so as to fill the time available for its completion

Several corollaries or restatements also exist with the same underlying message. This principle is usually attributed to human nature. In Lean/Agile development circles it inspires focus through concepts like:

* short Sprint lengths
* small User Story slices
* short cycle times with low variation

### Ziv's Law

Ziv's Law states that:

> software development is unpredictable and that the documented artifacts such as specifications and requirements will never be fully understood.[^zivs]

This has also been referred to as *The Uncertainty Principle in Software Engineering*:

>Uncertainty is inherent and inevitable in software development processes and products

Again, those familiar with the [Agile Manifesto] should be familiar with this law's influence on manifesto principles and focusing on conversations and iteration over formal specification.

### Hofstadter's Law

Anyone who has ever planned anything nontrivial should be familiar with this adage that states:

> It always takes longer than you expect, even when you take into account Hofstadter's Law.[^hofstadter]

The recursive nature of this law is inspiration for, among other things, breaking down tasks to hopefully minimize the optimism or uncertainty that is still present. It also highlights the frustration many experience with the process of estimating work.

### Humphrey's Law

This law describes an effect that has several other names: the centipede effect/syndrome (inspired by the poem [*The Centipede's Dilemma*](https://en.wikipedia.org/w/index.php?title=The_Centipede%27s_Dilemma&redirect=no)) or hyper-reflection.

>For a new software system, the requirements will not be completely known until after the users have used it.[^humphry]

The attribution goes to English psychologis George Humphrey who wrote about the difficulty performing tasks with conscious thought once those tasks had become unconscious habit. This effect may somewhat be related to the concept of [Analysis Paralysis](https://en.wikipedia.org/wiki/Analysis_paralysis) where over-thinking becomes the cause of delay or inaction.

In Agile software circles this law has also inspired the practice of iterative implementation of small slices of work with a high level of collaboration and review with the customer/stakeholder.

### Brooks' Law

>"adding manpower to a late software project makes it later"
>—Fred Brooks, *The Mythical Man Month*[^brooks]

One of the most common quotes, although all too often heard **after** having more people added to a late project. Brooks himself apparently referred to the law as oversimplification but it does force us to think about the impact of adding people and when. People have ramp-up time, require knowledge from others, and add to the complexity/communication needs of the implementing team. The fundamental message is that the costs are usually much higher than is often estimated.

### The Cone of Uncertainty

This project management principle describes how uncertainty changes over time[^coneuncertainty]. It describes that uncertainty tends to decrease over the course of a project, narrowed by reductions in variability. Variability is typically reduced through research and decisions that remove uncertainty. 

![Cone of Uncertainty](/img/640px-Cone_of_Uncertainty.jpg)

The *Cone of Uncertainty* can be found in applications like:

* Software project estimation and forecasting (a volatile environments that changes rapidly)
* Hurricane track forecasting (although in the opposite way than used in software, where uncertainty is highest now, not in the future)

Note that there are [some](https://plus.google.com/115091715679003832601/posts/FKLauKLZECm) [interpretations](https://leanpub.com/leprechauns) that question the validation and empiricism used in establishing the Cone of Uncertainty.

## Hardware

Software isn't very useful without hardware, is it? How does it impact us?

### Moore's Law

Moore's Law is:

> the observation that the number of transistors in a dense integrated circuit has doubled approximately every two years.[^moore]

While this is more of an observation, it has influenced product cycles that have anticipated or expected a certain level of computing power to be available when planning large scale products. In recent years the pace originally cited has slowed. This has influenced many observers producing software to shift toward better use of multiple cores/processors instead of anticipating increasing power in one. This changes the approach used in scaling for increasing computing workloads.

## Construction and Verification

### Wegner's Lemma ###

>"It is impossible to fully specify or test an interactive system designed to respond to external inputs"
>
>-- Peter Wegner[^wegner]

Similar to Ziv's Law and Hofstadter's Law, this lemma speaks directly to our ability to thoroughly describe either by document or executable specification (test) when we aren't fully control of what is sent to the system. Unfortunately, most useful systems require interactivity and some degree of external input.

No doubt that Wegner's Lemma inspired our next entry.

### Postel's Law (the Robustness principle)

Stated by John Postel who wrote a specification for the Transmission Control Protocol (TCP), this law/principle says:

> Be conservative in what you do, be liberal in what you accept from others (often reworded as "Be conservative in what you send, be liberal in what you accept")[^postel]

It is not surprising that this comes from a specifier of the TCP. In fact other works such as RFC 1122 went on to recommend against sending messages with legal but obscure protocol features the might expose issues on the receiving end.


### Lehman's Laws of Software Evolution

Of interest to those of us concerned with maintaining software products over time are the laws of software evolution formulated by Lehman and Belady[^lehman]. 

1. (1974) "Continuing Change" — an E-type system must be continually adapted or it becomes progressively less satisfactory
2. (1974) "Increasing Complexity" — as an E-type system evolves, its complexity increases unless work is done to maintain or reduce it[3]
3. (1974) "Self Regulation" — E-type system evolution processes are self-regulating with the distribution of product and process measures close to normal[3]
4. (1978) "Conservation of Organisational Stability (invariant work rate)" - the average effective global activity rate in an evolving E-type system is invariant over the product's lifetime[3]
5. (1978) "Conservation of Familiarity" — as an E-type system evolves, all associated with it, developers, sales personnel and users, for example, must maintain mastery of its content and behaviour to achieve satisfactory evolution. Excessive growth diminishes that mastery. Hence the average incremental growth remains invariant as the system evolves.[3]
6. (1991) "Continuing Growth" — the functional content of an E-type system must be continually increased to maintain user satisfaction over its lifetime
7. (1996) "Declining Quality" — the quality of an E-type system will appear to be declining unless it is rigorously maintained and adapted to operational environment changes[4]
8. (1996) "Feedback System" (first stated 1974, formalised as law 1996) — E-type evolution processes constitute multi-level, multi-loop, multi-agent feedback systems and must be treated as such to achieve significant improvement over any reasonable base

These laws are said to apply classes of system that are written to perform some read-world activity and adapt to varying requirements and circumstances in that environment. This is in contrast to programs written to an exact (comprehensive) specification or completely determine what a program can do.

These laws can help us understand concepts like Evolutionary Design, Technical Debt, and Building Quality In.

### Langdon's Lemma ###

>Software evolves more rapidly as it approaches chaotic regions[^langdon]

## Also Worth Considering

There are some others that are either that might be worth considering but I have had less time thinking through.

### Wicked Problems

Born out of challenges in urban planning is a class of problem call *Wicked Problems*. From Wikipedia, a Wicked Problem is:

> a problem that is difficult or impossible to solve because of incomplete, contradictory, and changing requirements that are often difficult to recognize. The use of term "wicked" here has come to denote resistance to resolution, rather than evil.

On the surface this resonates with me. Some of the resources below talk about applicability to software development, so I consider this worth further exploration.

Resources:

* http://en.wikipedia.org/wiki/Wicked_problems
* http://www.cognexus.org/wpf/wickedproblems.pdf 

## Takeaways

I find value in occasionally stepping back and re-reading these as a reminder. Sometimes this helps me think through a challenge I have encountered in a different way. Other times I end up just reinforcing my understanding. It is also interesting to reflect on just how validated each of these are, and whether there is more that can be done to prove or disprove these principles.

What laws, lemmas, or other useful conjecture should be considered along these? What have I missed?




[^law]: [Wikipedia definition of Law (principle)](https://en.wikipedia.org/wiki/Law_(principle))

[^brooks]: [Brooks' Law](https://en.wikipedia.org/wiki/Brooks’_law)

[^conway]: [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law)

[^parkinsons]: [Parkinson's Law on Wikipedia](http://en.wikipedia.org/wiki/Parkinson%27s_law)

[^zivs]: [H. Ziv and D.J. Richardson, May 1996.](http://www.ics.uci.edu/~ziv/papers/icse97.ps)

[^hofstadter]: [Wikipedia on Hofstadter's Law](https://en.wikipedia.org/wiki/Hofstadter%27s_law)

[^humphrey]: [Watts S. Humphrey, A Discipline for Software Engineering, Addison-Wesley, 1995.](http://en.wikipedia.org/wiki/Watts_Humphrey)

[^moore]: [Moore's Law](https://en.wikipedia.org/wiki/Moore%27s_law)

[^langdon]: [W. B. Langdon](http://www.cs.ucl.ac.uk/staff/W.Langdon/)

[^wegner]: Peter Wegner, Brown University ["Why Interaction is more powerful than algorithms," CACM 40(5):80-91, 1997](http://www.cs.brown.edu/people/pw/papers/ficacm.ps)

[^lehman]: [Meir M. Lehman and Laszlo Belady, 1974-1996.](http://en.wikipedia.org/wiki/Lehman%27s_laws_of_software_evolution)

[^postel]: [Postel's Law / Robustness principle](https://en.wikipedia.org/wiki/Robustness_principle)

[^coneuncertainty]: [Wikipedia on the Cone of Uncertainty](https://en.wikipedia.org/wiki/Cone_of_Uncertainty)

[Agile Manifesto]: http://agilemanifesto.org
