---
layout: post
title: A Hierarchy of Software Needs
excerpt: <p>How to take over existing software projects with extended metaphors</p>
---
In 1943 a psychologist, Abraham Maslow, published “A Theory of Human Motivation”. He was interested in identifying how human beings grow and develop. Fundamental to his approach was his “[Hierarchy of Needs](https://en.wikipedia.org/wiki/Maslow%27s_hierarchy_of_needs)”, which you’ll probably recognise:

![source: Wikipedia](https://dl.dropboxusercontent.com/u/2196291/MaslowsHierarchyOfNeeds.svg.png "Maslow's Hierarchy of Needs")

For each condition to be reached, the condition below must first be achieved. This structure he saw as helpful towards understanding human motivation at different stages of development. With this pyramid in mind let’s move to the field of Software Development.

## Context
I calculated recently that I have worked on well over 200 software projects in my career, on projects for large multinationals to small local charities.

Whenever I have been part of a team brought in to take over an existing service I was always
confronted with a pretty standard situation - a number of existing services, developed by a variety of different people, using different technologies and frameworks.

The work to do can always be boiled down to:

1. Support the existing services.
2. Develop new features.

There are always extra things to consider:

* Does the technology used in the old platform match the new team and ambitions?
* How many users does the service have?

## Challenges
As I am sure any of you who have been in this position know, there are always variants of the
same common problems, including:

* Running versions of software with known security defects
* No continuous integration, or patchy implementation across the stack.
* The time since the last production release can be uncomfortably long.
* Flaky tests (I hate flaky tests!). Test suites that succeed intermittently, or only in certain
places ('works on my machine!').
* ‘Frayed edges’: things like misfiring analytics code, _ye olde_ javascript, browser hacks for non-supported older browsers etc.

In addition there are all the standard things, design decisions that no longer fitted the use cases, legacy dependencies etc. etc.

What happened in the early stages of my career was that the new team would begin to solve these issues, but in a very ad-hoc way, depending on the current feature we were focussed on, or as in response to an incident. Often the issues would be **all** de-prioritised behind features. Solving theses issues then interrupted the delivery cycle, and left the development team feeling like they were unable to make commitments to releases, and the stakeholders losing trust.

## Thompson’s Hierarchy of Software Needs
At this point action is required.

In the first stages of my career I might have pushed for spending weeks not delivering features and just ‘fixing’ everything. This leads to very unrealistic development constraints, often a great deal of wasted time, and design decisions being made without the essential context of users and delivery.

Now I found it useful to define a hierarchy of software needs, to help us understand what actually needed doing.

![David Thompson](https://dl.dropboxusercontent.com/u/2196291/software-heirarchy.png "Hierarchy of Software Needs")

Each system needs to get to monitoring and analytics level, and by evaluating each system in the light of this diagram, we were able to prioritise and write technical tasks to cover the work. This focus, as oppose to a scattershot approach (often with random rewrites/refactors), meant that when each need was met we could move onto the next stage. It also articulated clearly to the team and stakeholders what the steps are.

Much of this is common sense, but by restricting yourself to the developmental stages in the hierarchy the team is able to focus and move the projects up to feature development stage much faster.

The heirarchy of needs also helps you to avoid writing vague technical tasks like ‘Ensure application is secure’. Instead ensure that all the stages to facilitate the developmental stage are in place before working on updating software versions and reviewing security.

Obviously your mileage may vary, and you may decide to prioritise differently depending on your circumstances. If you have a severe security risk, then this must be assessed and dealt with.

## And Finally…
I will definitely use the ‘Hierarchy of Software Needs’ metaphor in the future when inheriting projects. It provides focus and a way for us to demonstrate the need and value of our work to non-technical stakeholders. Thanks Maslow!
