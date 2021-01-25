---
layout: post
title:      "Planning Code with User Stories"
date:       2021-01-25 17:14:11 -0500
permalink:  planning_code_with_user_stories
---


![Classroom](https://edu.google.com/images/social_image.jpg)

The to-do lists, the bullet journaling, the note apps, and post-it notes that host a myriad of tasks. Much to do, yet such little time. Sound familiar?

Most would agree that ability to break down a project (such as a day’s events into manageable tasks) is key. In fact, the ability to plan and implement reasonable, actionable, and achievable steps is essential for success in nearly every industry.

For instance, let's examine my former career as a classroom teacher.

### When teaching, students come first

In education, teachers and staff use national standards as a guideline to support curriculum in the classroom. The common core documentation provides a specific outline of achievable units, and it is the teacher’s job to develop a framework for learning. Take the following Common Core standard:

> [CCSS.MATH.CONTENT.K.CC.A.3](http://www.corestandards.org/Math/Content/K/CC/)
> Write numbers from 0 to 20. Represent a number of objects with a written numeral 0-20 (with 0 representing a count of no objects).

Using this as a guide, a teacher may outline their lesson plans with a student’s success in mind. Let’s use the fictitious student Pomona as a guide:
 
> As Pomona, I want to write numbers 0 to 20 so I can represent the number of potted Dittany plants I have.

By shifting the perspective from the Common Core documentation and lessons on the person, to the actual student, a knowledgeable teacher can implement lesson plans that incorporate a students’ interest to maximize effectiveness.

Pomona will be thrilled to know that she can write down the number of potted Ditty plants she has.

### Planning to Teach, Planning to Code

Now let’s explore a different industry: software development.

I’m currently in the process of building a [Ruby on Rails application named "Karl"](https://github.com/cglorious/karl-rails-app). Karl the app manages related data in the form of reviews through complex forms and RESTful routes. And in case you're wondering, the app is conveniently named after the infamous ["Karl the Fog"](https://twitter.com/karlthefog) from San Francisco. 

![Karl the Fog](https://s.hdnux.com/photos/64/04/70/13651494/4/rawImage.jpg)

The goal Karl the app is to build a Content Management System in the form of customer reviews. I used it as an opportunity to recreate a localized business review system in San Francisco.

While planning the build, I couldn’t help but notice the similarities in the planning process from my former career in the classroom to that of software development. The ability to break down a large goal into small, actionable items yet again benefits productivity. Whereas the person in the classroom is the “student,” the person in software development is referred to as the “user.” 

While it is possible to solely teach all lessons from the curriculum provided by the district, many classroom teachers would agree that that’s not the reality. Without putting the students’ needs first, differentiating instructional strategies or peaking students’ interest is near impossible. Similarly, in programming coding without the intent of the user may be possible, but is hardly effective. 

### When programming, users come first

So let’s say it’s been quite some time since grade school, and Pomona’s love for plants has blossomed (yes, pun intended). In fact, she has many more potted Dittany plants. In fact, she has excelled to a career in Herbology, and needs a process to store information about all of her plants.

By implementing ***User Stories*** in the planning aspect, we can plan our code effectively. But before we help Pomona, let’s backtrack and first understand a few details related to User Stories.

![User Story](https://www.scrumwithstyle.com/wp-content/uploads/2018/02/User-Story-Card.png)

**Who?**

User Stories are used by developers, stakeholders, and team members. It’s content is derived from users who contribute to the data.

**What?**

The implementation of User Stories is an approach that allows customer centric conversations to exist. In its structure, there are a few key features to note:

INVEST
* **I** ndependent of one another
* **N** egotiable; able to capture the essence of the user’s need
* **V** aluable; delivers value to the end user
* **E** stimate; ability to be estimated to be properly prioritized
* **S** mall chunks of work, to be completed in 3-4 days
* **T** estable; pre-written acceptance criteria

SMART
* **S** pecific
* **M** easurable
* **A** chievable
* **R** elevant
* **T** ime-boxed

CCC
* **C** ard - Who, What, Why?
* **C** onversation - conversations with product owners, stakeholders, and team
* **C** onfirmation - conditions of satisfaction that indicate completion

**Why?**

The purpose of implementing User Stories is to articulate how software features will provide value to the customer. Planning from the customer’s perspective gives a framework to allow for the ability to deliver software quickly. It captures and prioritizes requirements for sprints.

### Back to the (User) Storyboard

To keep things succinct, we’ll support Pomona by focusing on the initial construction of a User Story, or “Card” in the CCC example above. 

> 1. Who is it for?
> 2. What is expected from the system?
> 3. Why is it important?

Now let’s use this framework to devise a way to support Pomona’s needs.

> Q: Who is the user?
> A: Pomona
> 
> Q: What does Pomona want?
> A: An app that acts as a database
> 
> Q: Why does Pomona want a database app?
> A: To care for her plants easily

When crafting a User Story, it can be accomplished in a brief sentence:

> As [ role ]
> I want to [ action ]
> so [ benefit ].

Following this simple framework, we can create our User Story.

> As Pomona, I want an app to act as a database so I can care for my plants with ease.

Now that we understand the overarching task, let’s continue the process to break the User Story into manageable tasks. 

I wonder... Would Santa Claus benefit from implementing User Stories framework when planning the build of toys in his workshop? Inquirying minds want to know.

![Santa's List](https://learnhowtowriteanovel.com/wp-content/uploads/2018/12/santa-1908027_1280-Elizabeth-Goddard.jpg)

### Breaking it down

Refocusing our efforts from the workings of Santa Claus and to our user (Pomona), it's time to make our own list of tasks through User Stories. With our end-user goal in mind, we can use the User Story framework to determine manageable tasks.

```
[   ] As Pomona, I want to sign up so I can create my account.
[   ] As Pomona, I want to view my plant collection so I can remember plant care details easily.
```

As more User Stories are added to the list, I categorize tasks by functionality. Segmenting tasks into categories allows me to understand and implement routes, models, controllers, and views. In a pair programming or group setting, it also sets the framework for a delegation of tasks.

```
Signup, Login, Logout
[ x ] As Pomona, I want to sign up so I can create my account.
[   ] As Pomona, I want to login so I can use my account.

My Profile
[   ] As Pomona, I want to view my plant collection so I can remember plant care details easily.
```

Keeping in mind an app will most likely be used by more than one person, I find it useful to add additional users as the program is built. My thought is this: users tend to prioritize app functionality in different ways, so why not highlight that in the planning process?

```
Signup, Login, Logout
[ x ] As Pomona, I want to sign up so I can create my account.
[ x ] As Pomona, I want to login so I can use my account.
[   ] As Pomona, I want to logout so I can protect my information.

My Profile
[ x ] As Pomona, I want to view my plant collection so I can remember plant care details easily.
[   ] As Pomona, I want to edit my profile.
[   ] As Myrtle, I want to delete my profile so no one knows I was here.

Stretch Goals / Feature Request
[   ] As Myrtle, I want to create a ghost profile so I can view other profiles only.
```

With our growing to-do list in place, we are ready to code. Pomona will be thrilled, I just know it.

![Pomona](https://static2.cbrimages.com/wordpress/wp-content/uploads/2020/07/professor-sprout.jpg)

### Storytime while coding

I find the implementation of User Stories particularly effective during the planning process, and throughout the build of the app. It provides a framework for continuous development. While by dividing work into manageable tasks. I often found myself referencing the User Stories at the start of each coding session, if I felt stuck on a certain concept, and at the completion of each sprint.

User Stories helps me identify the app needs, or [Minimum Viable Product (MVP)](https://www.agilealliance.org/glossary/mvp), versus stretch goals. In the example above, the ability to logout is essential, and is a manageable task to achieve. The ability to create a ghost profile, not as much. As I identified the stories that were more wants than needs, I created a subsection for stretch goals to be targeted at a later time.

Upon the completion of the pseudo plant app, Pomona will be thrilled to know that she can create a virtual greenhouse in order to store information about her plants, including her potted Ditty plants.

Apologies, Myrtle. We’ll keep your ghost profile concept in mind for future updates.

![Myrtle](https://static0.srcdn.com/wordpress/wp-content/uploads/2019/10/Moaning-Myrtle.jpg)

### Continuing the growth mindset

A simple app idea can seem quite intimidating at the forefront, and one can easily get lost in the code. User Stories can help maintain focus of the end-goal, providing checkpoints for completion along the way.

While I found this process of implementing User Stories particularly helpful in planning, building, and debugging code, I would highly advise reviewing additional resources. As is required in both education and software development, exploring additional sources and documentation is an ongoing process. Please respond if there is any additional documentation that aligns with the content of the information above.

* [User Stories with Examples and Templates](https://www.atlassian.com/agile/project-management/user-stories)
* [What is User Story?](https://www.visual-paradigm.com/guide/agile-software-development/what-is-user-story/)

