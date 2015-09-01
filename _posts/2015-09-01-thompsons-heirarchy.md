---
layout: post
title: Thompson’s Hierarchy of Software Needs
excerpt: <p>How to take over existing software projects</p>
---
# Thompson’s Hierarchy of Software Needs
In 1943 a psychologist, Abraham Maslow, published “A Theory of Human Motivation”. He was interested in identifying how human beings grow and develop. Fundamental to his approach was his “[Hierarchy of Needs](https://en.wikipedia.org/wiki/Maslow%27s_hierarchy_of_needs)”, which you’ll probably recognise:

![source: Wikipedia](https://dl.dropboxusercontent.com/u/2196291/MaslowsHierarchyOfNeeds.svg.png "Maslow's Hierarchy of Needs")

For each condition to be reached, the condition below must first be achieved. This structure he saw as helpful towards understanding human motivation at different stages of development. With this pyramid in mind let’s travel back in time together to early 2015…

## Context
Recently I have been lucky enough to join a newly formed agile (no, really!) software team in Leeds, UK. We were confronted with a pretty standard situation for a new development team - a number of existing services, developed by a variety of different people, using different technologies and frameworks. We had two things to do:

1. Support the existing services
2. Develop new features for product owners.

We also had to consider:

* 90% of the existing software was written in Ruby. I was the only person with real Ruby experience on the team.
* The services are used by a **lot of people**, every day.
* We wanted to play our part in delivering the feature roadmap, and achieving the goals of the wider business.

## Challenges
As we began work a variety of issues cropped up across the projects, including:

* Some were running versions of software with known security defects (though nothing high risk, thankfully)
* Some were hooked into our continuous integration system. Some weren’t.
* Releases to production environments hadn’t taken place for over a year in some instances.
* Flaky tests (I hate flaky tests!), that would run 60% of the time. Did I mention I hated flaky tests?
* ‘Frayed edges’: things like misfiring analytics code, _ye olde_ javascript, browser hacks for non-supported older browsers.

In addition we had all the standard things, design decisions that no longer fitted the use cases, legacy dependencies etc. etc.

What was happening was that these issues were beginning to get solved, but in a very ad-hoc way, depending on the current project we were focussed on, or as in response to an incident. Solving theses issues broke our delivery cycle, and left the development team feeling like they were unable to make commitments to the business

## Thompson’s Hierarchy of Software Needs
At this point we knew we needed action!

In the past I might have pushed for spending weeks not delivering features and just ‘fixing’ everything. This leads to very unrealistic development constraints, often a great deal of wasted time, and design decisions being made without the essential context of users and delivery.

Instead I found it useful to define a hierarchy of software needs, to help us understand what needed doing and when.

![David Thompson](https://dl.dropboxusercontent.com/u/2196291/software-heirarchy.png "Hierarchy of Software Needs")

We knew we had to get each project to monitoring and analytics level, and by evaluating each project in the light of this diagram, we were able to prioritise and write technical tasks to cover the work.

Much of this is common sense, but by restricting ourselves to the developmental stages in the hierarchy we were able to focus and move the projects up to feature development stage.

The diagram also helped us avoid writing vague technical tasks like ‘Ensure application is secure’. We could instead ensure that all the stages to facilitate the developmental stage were in place before working on updating software versions and reviewing security.

Obviously your mileage may vary, and you may decide to prioritise differently depending on your circumstances. Our applications were already on a robust, secure infrastructure so we were able to ensure tests were in place before updating dependencies. We also evaluated the risk involved in not updating dependencies until tests were in place. If you are running a known vulnerable piece of software then you may have to expedite security, at the risk of quality.

## Microservices! Rewrite all the things!
We are lucky that the services we were inheriting were part of a sound larger architectural vision. Each one could be termed a microservice. In fact, as we worked our way up the hierarchy we decided on a few occasions to decommission the service and rewrite it from scratch.

This was both a great exercise in the team ‘owning’ our infrastructure and in reducing technical debt. On most occasions it also resulted in less, more enjoyable work overall. We would not have been able to carry out these rewrites without decent  test coverage.

Inspired by the work of a developer on our team in node.js and koajs, we also chose to move from a primarily Ruby focus to a JavaScript focus - both to match the skills of the team and also to meet our use cases.

## And Finally…
I will definitely use the ‘Hierarchy of Software Needs’ metaphor in the future when inheriting projects. It provided focus and a way for us to demonstrate the need and value of our work to non-technical stakeholders. Thanks Maslow!
