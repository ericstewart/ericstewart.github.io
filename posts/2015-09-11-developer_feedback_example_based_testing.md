title: "Developer Feedback Mechanisms: Example-Based Testing"
url: /blog/developer-feedback-example-based-testing/
description: "Software Developers need good feedback mechanisms. The example-based test is one of the most frequently leveraged."
excerpt: "Software Developers need good feedback mechanisms. The example-based test is one of the most frequently leveraged."
date: 2015-09-11
modified: 2015-09-29
image: /img/developer_feedback_ebt_banner.jpg
thumbnail: /img/developer_feedback_ebt_banner.jpg
tags: feedback,testing
classes:
- feature-figcaption
- feature-figcaption-hidden
- feature-figlink
- feature-fignum
- feature-tablecaption
- feature-highlight

I like the term ***feedback***. As Wikipedia describes it:

> Feedback occurs when outputs of a system are routed back as inputs as part of a chain of cause-and-effect that forms a circuit or loop. The system can then be said to feed back into itself.[^wikipedia_feedback]

As software developers, we should always consider the value we get out of the many activities we use to deliver software. All too often someone champions the latest tool or practice because it is new, interesting, or just *seems right*. Or perhaps it is because everyone -- or the just the right people -- seem to be doing it (you may have heard this referred to as [cargo culting](https://en.wikipedia.org/wiki/Cargo_cult_programming)). And so we try out whatever it is, maybe getting value, maybe not.

I certainly advocate experimenting with something in the hopes of improvement. But along with this goes some guess of what this new tool or technique will provide that we can validate. For me, *Feedback* is at the top of the list. I like to think of when, and how we get feedback and how it will be used to make things better.

I especially like the definition of 'feedback' above because it encourages a [*"systems thinking"*](https://en.wikipedia.org/wiki/Systems_thinking) view.  Just as employees can benefit from peer feedback and companies benefit from customer feedback, we software developers can benefit from our own feedback mechanisms. Feedback can come in many forms about different aspects of the product: Design, behavior, performance, maintainability, etc. We are part of a complex system where just part of it is a person at a computer making code changes using an editor or IDE.


![Simple Feedback 02 by Trevithj](/img/Simple_Feedback_02.png)
_CC BY-SA 3.0 via Commons_

https://commons.wikimedia.org/wiki/File:Simple_Feedback_02.png#/media/File:Simple_Feedback_02.png_


In this, the first of a series on developer feedback mechanisms, I start with one of the most commonly encountered developer practices that provide a feedback loop: Example-based Testing. 

## Example-Based Testing

What better topic than this to start with an example!

I would have a difficult time finding a Java programmer that isn't somewhat familiar with [JUnit]. Pick almost any language or stack and there is a similar testing framework available. Fundamentally, such frameworks support writing code that is not intended for production release that exercises other code that is meant for production.

Imagine we have a `Calculator` class designed to evaluate strings with mathematical expressions. To gain confidence in the code, we can think of a specific interaction we need to make and the expected result and then turn this into an executable test. In many languages it would look similar to this Java example using the [JUnit] framework[^junit_example]:

```java
public class CalculatorTest {

    @Test
    public void evaluatesTripleOperandAdditionExpression() {

        // Set up the test
        Calculator calculator = new Calculator(); 

        // Call the production code
        int sum = calculator.evaluate("1+2+3");

        // Verify that everything is as expected
        assertEquals(6, sum);
    }
}
```

This test has a context using a `Calculator` object with no explicit configuration or prior usage. As described in the name it is focused on the example of triple-operand addition, so the test uses the `calculator` object this way by passing a string to evaluate. Finally, it asserts that result is correct and that the `calculator` correctly determined the operators and operands in this string and calculated the correct result. 

If you have done any automated testing you were probably introduced to testing this way. Many of the most popular testing frameworks were created with this approach in mind: [JUnit], [NUnit], [test-unit], etc. However, while most commonly used to test lower level units of code (classes, methods, etc), you can also target collaboration between objects, modules, components, etc.

What may be new to you is the label for this style of test: Example-Based Test. But that is exactly what is going on here. All the components  of the test -- the setup, using the code, and verifying what happened -- all are based on some example of what is expected of the test subject. 

A programmer using this style of testing iteratively constructs example after example (building a unique test for each) until she considers the set of tests to be complete enough for the task at hand. 

### Feedback

What feedback did we get in the example above? I can think of a few types:

* The calculator can *at least* gives us the right result for the string `"1+2+3"`
* The code under test can give the correct result with the default configuration (if there is any ability to configure at all) and with no prior operations performed.
* The developer writing the test can get a sense of what it is like to use the `Calculator` to perform this task: She is taking on the perspective of a user

What don't we know yet?

* If it works with the same operators and different operands
* If it works with other operators and the same operands
* If it works with a different number of operands (still using just the addition operator)
* If it works evaluating this string following evaluation of anything else
* What are the largest numbers we could pass in that work?
* Does it work with floating point numbers?
* ... We could go on

Certainly we will need some more examples (and thus tests) to get more confidence that the `Calculator` does the right thing. But we just listed out some examples above as a start to that. And we *might* even be able to sit down with a potential user (even a non-programmer) that could one day want to perform addition through an application that uses this code and get some more examples.

Sometimes the setup, execution, or verification steps become challenging to write in a test. The experience of using the API being tested is yet another form of feedback about things like design, usability, and testability of the code. Based on the feedback of creating the test, we might want to change the design of the external interface of the code under test.

There are other ways to help address some of these challenges, such as Test-Driven Development, which I'll cover in another post. 

### When Is It Used?

Feedback is most valuable when it is **timely**. The later a problem is discovered from when it is created, the more likely its resolution is to be rushed, postponed, or dismissed. Fortunately, example-based tests are well suited for creating and running early in development and then running frequently during the lifetime of the product features they describe.

Consider when a developer creates an example-based test alongside the production code they are working with. All those things we stand to learn from creating and running the test are discovered pre-commit when they are least expensive to address. And when they check in both passing test and code together, the commit will essentially always be somewhat self-documenting.

So some developer discipline is needed to execute these tests frequently. We need to trust the developer making the change to run relevant tests and confirm they pass. Conveniently, many software stacks today have tooling that will help run targeted tests in the background based on the code that is being edited. If care is taken to use good testing practices, lower level (especially unit tests) that are example-based can normally be kept quick enough that their regular execution does not become a bottleneck.

These days most development teams hopefully use some form of Continuous Integration or build server. This is a great way to run a whole suite of tests more frequently, such as on any check-in. That way we get feedback on whether the behavior of *any* of the system changed unexpectedly. This is helpful for when it is prohibitively expensive for an individual developer to always run comprehensive tests before check-in, and this practice keeps the feedback loop relatively close as long as tests aren't run too long after check-in.

### How Do I Start?

With so many great options for common software stacks, this shouldn't be too hard. Basically, you need to:

1. Make it easy to add tests - add a test framework to your code base and bootstrap an example test
2. Make it easy to run tests - add targets or scripts to build scripting, IDE tooling, so that everyone can easily execute the existing tests
3. Document how to add new tests and make sure everyone understands how

Once you and your team begin using these tests and gaining confidence, you can add tasks to Continuous Integration builds to execute and notify if problems are found.

### What Are the Challenges?

As with most activities, Example-based tests can be misused and be more hindrance than help. I like to say that these are situations where they fail to provide good, timely feedback. So after you start using Example-based testing look for the following:

* Keeping the tests fast enough that they are regularly executed
* Knowing when you have tested enough
* Test Smells or Antipatterns present, such as side-effects from other tests, testing the wrong thing, overly complex setup, difficult readability, missing examples
* Isolating what is being tested (to minimize false results due to a problem with collaborating code) and making pinpointing the real problem more challenging
* Ramp-up/learning time (like any new practice adoption is slow in the beginning)

### Where Is It Not A Fit?

It is really difficult to come up with exclusions here, but one of the most often cited places to avoid writing example-based tests is for code you don't own/control. That being said, I know people who use example based tests (at least temporarily) when evaluating a new library they are exploring. 

What about cases where there are many potential inputs/outputs and thus a large number of examples are possible (or required) to gain confidence in system behavior? This is not uncommon with testing algorthims and there are complementary styles of testing that can be helpful in these cases that will be described in later posts.

## Wrapping Up

Hopefully a *feedback*-oriented view of example-based testing helps you experiment and set expectations of value. I will certainly cover other testing-related topics in looking at ways that developers can leverage feedback.

---

**Footnotes:**

[^wikipedia_feedback]: [Wikipedia on Feedback](https://en.wikipedia.org/wiki/Feedback)
[^junit_example]: Inspired by an example from the JUnit Wiki's [Getting started](https://github.com/junit-team/junit/wiki/Getting-started) page

[JUnit]: http://junit.org
[NUnit]: http://nunit.org
[test-unit]: http://test-unit.github.io
..
