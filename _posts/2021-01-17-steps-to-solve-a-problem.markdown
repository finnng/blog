---
layout: post
title:  "Steps to solve a problem"
date:   2020-11-26 20:52:33 +0700
categories: blog
---

 Problems in software come in many kinds, it can be a user story, a bug, a discussion. As a developer, our job is solving problem day-to-day, but we rarely think of how we solve it as the process.
 Here I will jot down somethings from my experience.

### 1. Define the problem

The problem should be a statement, clear, and focus on the main evolving actors. Even if we have a big discussion with the huge amount of work needed or just a small task when it comes to our mind to really work on it, it is a small unit work just fits in our head for a few working hours.

Otherwise, we will few overwhelmed with the unclear statement.

An effective way to sentence a problem is a user story, for example,
`As a user, I want to do X, so that I can achieve Y`

To define a bug, we have the form like
`When I perform X, the system resulted in Y, but I expected Z`

### 2. Gather information

As you can see, it will much easier when the problem statement is clear. Now we need to gather information, the key here is just to keep the focus on the main actors of the user story/bug report. Usually in a big system, when we change something it won't just change what we mentioned in the statement, the other parts of the system may malfunction as we change this part, and it is normal. Our job here is to aware of it and adjust the requirement to cover all the impacts.

For example, a user story like,
`As a user, I want to delete an old campaign from the campaign page, so that I can get rid of managing the used campaigns`

1. To see how a campaign record disappeared will impact the system, I will check the relations of it in the database, usually, this is a direct level of impact
2. Then based on my experience to see which part of the system will malfunction if the record was deleted
3. Finally, ask someone with the most knowledge

As a result of investigating and gathering information, sometimes the problem will need additional works, adjust to bigger or smaller. We will bring it all to the discussion and the result will be another user stories/bug reports.

### 3. Find the solution

My favorite part is to find a solution, aren't we all? The result of this step is the Solution Review document.

The process should be, I spent sometimes think of the problem, then write it down as the solution review document, and ask the team for the approval or discussion if needed, then go ahead.
The solution review document usually includes all the information from steps 1, 2, and 3. Sometimes it needs a higher level of management to approve, it all up to you to raise the level if you think it's important or costly.

### 4. Solve the problem with the solution

One takeaway key from this step is to apply the agile mindset when implementing the solution. We can think of each release is an MVP (minimum viable product).

For example, we have the problem with a page without the paginator and it only shows a limit of record to the user, which prevents them from seeing all the records, we first just hard code the number of records from 30 to 100, then deploy the code changes to satisfy that particular user. Then implement the paginator.

The solution may come with several steps, we should have the todo list for, and check it frequently, even a small one. I found this practice brings me the feeling of archiving and motivating.

### 5. Release and get feedback

This step won't far away from step 4, we keep circulating between steps 4 and 5 until all the problems solved. As you can see, deliver a small MVP will easier to get feedback and easier to fix if we went wrong.
