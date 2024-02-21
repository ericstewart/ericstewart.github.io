title: Developers -  Write Like You Code
description: As a developer, how can you get feedback when writing for humans similar to what you have when writing code?
date: 2015-06-09
tags: writing,feedback
thumbnail: /img/Bios_robotlab_writing_robot_medium.jpg
Image: img/Bios_robotlab_writing_robot_cropped.jpg
# creditperson: Mirko Tobias Schaefer
credit: https://www.flickr.com/photos/gastev/2174504149/

I spend more and more time writing things other than code these days. As a developer, programming is important but communicating well with others is equally valuable. Depending on what kind of role and environment they are in, a developer can easily find themselves crafting or contributing to a number of types of written communication. For example:

* Code comments and commit messages
* Documentation, wiki pages, or knowledge bases
* User Stories, scenarios, requirements, or other types of specification
* Blog posts and social media posts
* Marketing or web site copy
* Proposals and agreements

Some of these have not always been common activities for me and have become more frequent over the years as responsibilities, roles, and companies, have changed. As I have progressed the need to write well has become increasingly important.  If this resonates, you might (as I have) look for feedback mechanisms that can help. 

## Writing Feedback

When I am writing code I rely heavily on feedback mechanisms to help me end up with a good result in a short period of time. I'm heavily influenced by the technical practices, workflows, and lean/agile approaches I have learned over the years. For example:

* Automated Tests
* Test-Driven Development
* Pair Programming
* Code Reviews
* Continuous Integration
* Static Analysis

Since those types of feedback have been so valuable when writing code I looked for similar mechanism when writing. If you have ever used a word processor you have probably used a spelling or grammar checker. Those are useful tools, but what else is available?

What follows are some of things I have used or have been experimenting with.

1.  **Stepping away from the keyboard**

    This is a simple one. After writing a bit and I feel finished, stuck, or unsure, a good walk or short break often gives me just enough of a rest to spark a new perspective or fresh view when I resume writing. Sometimes, if time allows, just sitting on it overnight does even more good as it gives my mind some background processing time to think about what I've written.

    This approach requires no one else and is fairly low cost as long as you manage time well.

2.  **A Review from Someone Else**

    A review from another person is some of the best feedback you can get. You get help with understanding, clarity, different perspective, and sometimes new ideas. If you can solicit multiple reviewers this is even more effective.

    This comes at a cost, however, as other people usually have plenty of time constraints themselves. Often you will only get one round of this type of feedback.

3.  **Pair Writing**

    As with Pair Programming, the benefits of having another person working with you in real time are huge. You get more than one perspective on the content, in-line editorial comments, and get to toss around multiple ideas sometimes before a single word makes it on the page.

    This is most commonly done at a single computer with one person typing and the other guiding with ideas and real-time review. As with Pair Programming, you need a strategy for switching the person at the keyboard, but the end result usually requires far less additional review.

    An enjoyable variant of this requires two devices and a bit of tooling. This involves two writers working on the same document at once. I have mostly done this using a Google Doc which allows real-time editing/review from more than one user. I have worked on documents with two of us writing different sections while a third person reviews and comments. This is a great way to use a group of people to swarm on a document and get it written/reviewed quickly. This has been helpful for proposals, blog posts, web site copy, etc.

    This requires more than one person but can get you to solid written content more quickly.

4.  **Readability Statistics**

    Somewhat similar to failing tests or static analysis metrics, having some quantitative feedback while writing can help indicate when things are off track. In addition to spelling and grammar checking assistants there are tools that provide statistics and [readability](http://en.wikipedia.org/wiki/Readability) [tests](https://en.wikipedia.org/wiki/Flesch–Kincaid_readability_tests) on writing that can be easily used.

    There are number of these to explore. Since I write so much content using [Markdown] I usually use [Marked 2] to preview my document as I save it. [Marked 2] includes a few different views that display statistics such as:

    * Count of Words, Characters, Paragraphs, Sentences
    * Average Words/Sentence, Average Syllables/Word
    * Percentage of Complex Words
    * [Reading Ease](http://www.readabilityformulas.com/flesch-reading-ease-readability-formula.php)
    * Grade Level
    * [Fog Index](http://en.wikipedia.org/wiki/Gunning_fog_index)
    * Estimated reading time

    These are the statistics for this blog post: ![Marked 2 Statistics](/img/marked2_statistics.png)

    Each of these require a little learning to understand what they are telling you but might give you an indication that the content could be simpler or otherwise improved. Also, when you make edits you can see the effect of your changes. As with any metrics, these don't guarantee that your writing is good or well communicated, but certainly can help indicate when things are off track.

    When integrated into an editor, this feedback can be almost automatic and run frequently. Without direct editor or previewer support there are still a number of tools to provide this kind of analysis. These are just a few:

    * [readability-score.com](http://readability-score.com) - Provides analysis on text pasted in page, from a provided URL, or uploaded to the site and can even handle PDFs and Microsoft Word and have a bookmarklet available.
    * [read-able.com](http://read-able.com) - Another web site that supports readability tests via URI, direct input, referer, or bookmarklet
    * Newer versions of Microsoft Office and Outlook appear to have readability statics [built in](https://support.office.com/en-us/article/Test-your-documents-readability-0adc0e9a-b3fb-4bde-85f4-c9e88926c6aa) if you enable them.

5.  **Listening**

    Has someone ever asked "Do you hear what you are saying?" Sometimes just reading aloud (to prevent skimming) can help identify problems in clarity, flow, grammar, etc. Give it a try!

    I have been trying another approach to this by using speech synthesis on my computer to read back what I have written and I focus on listening. I'm sure I picked up this idea from somewhere but can't remember where but I have been enjoying it. I get to try out what I have written as a listener and usually I try not to read along. This seems to help for a number of reasons, most likely that it has the benefit of trying out the content using another sense.

    There is another bit of feedback that comes from this approach. While speech synthesis has improved in recent years, it is still less capable when complexity or word choice get out of control. I have found that when the speech tool has trouble pronouncing a word or making a sentence seem fluid there probably is a simpler way to write the text.

    Getting this kind of feedback can be pretty easy. There are a number of speech synthesis tools out there, many inexpensive. Since I am on a Mac I use the built in Text-to-speech tool which lets me easily highlight and have certain sections, paragraphs, or even sentences read from most applications.

## Regular Practice

As the saying goes: *"Practice Make Perfect"*. Regular blog posts can help as well as writing a little every day. In addition to blogging, daily journaling can be another easy way to practice and can be as simple as using text files, tools like [Evernote](http://www.evernote.com), or a dedicated journaling application like [DayOne](http://dayoneapp.com/).

## Summary/TL;DR

Writing (effectively) is an important skill for developers to have. Developers used to many different feedback mechanisms while writing code can find similar types of feedback when writing. Experiment with some and get in regular practice. Your teammates, collaborators, users, and customers will appreciate it!


[Markdown]: http://daringfireball.net/projects/markdown/
[Marked 2]: http://marked2app.com

