---
layout: post
title:  "Build an exceptional team: hiring"
image: '/assets/blog-images/hiring.jpg'
excerpt: >
  Excellent hiring is the number one way to make or break your startup. Having a standardised approach pays wonders. I found that following a Tasks-Skills-Questions method helped me hire exceptional people.
---

> **TL;DR** <br/> {{ page.excerpt }}

It was a beautiful, sunny, late-autumn day in London. However, the mood in the meeting room was anything but sunny. I was with the other two co-founders of [DeepStream](https://www.deepstreamtech.com/), the startup we had started just a few months earlier. Out of the six very first people we had hired, we already had to let go three of them. We were not downsizing, actually we needed to hire again, asap. It was not that they were not skilled either, quite the opposite. It just felt that we had hired people with different skills than our actual needs. Sometimes I learn the hard way, and this was such a case. This incident was the trigger for me to reflect deeply on what we did wrong and change our interviews. The results were impressive. Within a few months we had build the strongest dev team I have ever worked in!

<img src="{{page.image}}">

## Hiring the wrong way

The very first time I faced the task of hiring someone, I turned to the [one that knows everything](https://www.google.com/) with questions like *"interview questions for javascript/react/angular/whatever-else developers"*. Give it a go. Thousands of results come up. Click-bait blogs dominate, but still you can find a lot of interesting questions to ask. The problem though with using this type of questions is that they drive you to assess people on their hard skills which, in my experience, are far less useful than some of the soft skills a good developer needs. You test your candidates on javascript trivia, which is not directly related to performance.

Say for example that you ask someone *"what is a higher order component (HOC) in React?"*. A decent React developer will certainly be able to answer this question easily. However, an exceptional developer who has been working with Angular will strugle. If hired though, the latter will pick up HOCs in a couple of days and he will deliver high-end code for years. On the other hand, a less competent developer that has been working with React for a couple of years, most probably will answer correctly, and if hired he will go ahead and create messy, over-engineered, spaghetti-code HOCs all over the place. Between the two, you want to hire the first one, and you need to tailor you interview to distinguish between the two.

## A better way to hire: Tasks - Skills - Questions

The method that worked for us, was to answer those three question regarding our future employees:

> 1. What do we need them to deliver?
> 2. What skills do they need to have *before* being hired to deliver it?
> 3. How can we probe for those skills at the interview?

Write down the answers using bullet points. Make it explicit, terse and to-the-point.

## Example #1
Let's assume that we are a small startup is and we are hiring for a senior full-stack developer. Our stack is React, Express, Node, MongoDB, AWS.

### Step 1: What do we need them to deliver?
- **Contribute clean code**, back-end and front-end.
- **Contribute to application architecture**. It includes anything from databse schema, to deployment, to directory structure of source code etc.
- **Take initiative and ownership of introducing new libraries/tools**. Eg if the application does not have automated tests, they should be able to choose libraries, introduce them, write the first working examples and mentor junior devs how to add more tests.
- **Be able to "own" features**. When an abstract requirement for a new feaure comes in, they should be able come up with a database schema that solves the problem, write back-end code in express and front-end code in React, and also come up a UI design that works for the user.
- **Fit culturally with the team**.

### Step 2: What skills do they need to deliver it?
- Be **talented and love coding**.
- Deep knowledge of **web technologies**: HTML, CSS, JavaScript.
- Above average understanding of **databases**.
- Experience with a **modern JavaScript framework**.
- Experience with **delivering production code**.

Note that there are no right/wrong answers here. Every role in every company is diffent. For example, maybe we use ElasticSearch heavily and the existing team lacks an ES-expert. In that case the candidate *needs* to be strong in ES *before* being hired. Even though in a different setup we could train a good developer into ES, in this situation we cannot afford to.

### Step 3: How can we probe for those skills at the interview?
- Probing for talent, passion and aptitude for clean code is the hardest. What I have found is that people that people who love code have at least a few of the below:
  - They started coding at young age.
  - They have read some of the industry's famous books.
  - They have a github account.
  - They have community presence: meetups etc.
  - They have side projects.
  - They have used weird techs, eg yacc etc.
  - They have their own blog.
  - They have favorite bloggers / youtubers.
- Regarding hard skills, ask above-average questions on:
  - JavaScript (eg ES6 features, closures).
  - Databases. Ensure they understand basic concepts both in relations or no-SQL systems.
- Ask about past work experience: you need to ensure that:
  - They were coding daily with React or Angular or Vue.
  - They wrote a lot of HTML/CSS.
  - They commited production, ie code that *had* to be correct.
- Ask what other stacks they have used in the past. Avoid one-trick ponies, they might not be flexible enough to adapt. Don't be impressed by too many buzz words, they might not be able to go deep in any of them.

## Main take-away
Every role is different and even even the same role might require different skillset depending on the rest of the team. Instead of asking canned question at the interview, think what you want the new hire to deliver, what skills they need to deliver it, and then probe for the skills that you cannot afford to teach them after they get hired.
