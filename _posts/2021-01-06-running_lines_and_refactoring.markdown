---
layout: post
title:      "Running Lines and Refactoring"
date:       2021-01-06 20:42:36 -0500
permalink:  running_lines_and_refactoring
---

![Theater](https://howtodrama.com/wp-content/uploads/2019/02/audience-auditorium-back-view-713149-1080x675.jpg)

In preparation for a performance in the theatre industry, it is essential for an actor to run lines. Running lines is the act of reading and interpreting continuously until there is fluid motion in the delivery of the text. Similarly, writers write and rewrite. Software developers code and refactor.

> "The only type of writing is rewriting." - Ernest Hemmingway

I find several similarities in my role as a performing artist and my role as a software engineer. After all, coding is a creative process. Like other creatives, software engineers use their imagination, creativity, and skillset to ultimately produce an artistic piece of work that doesn't exist. It is executed through the lines of code.

### The Plan

Initially, I was tempted to build a complex app with not only **belongs to** and **has many** relationships, but multiple types of users and **many-to-many** relationships. It took me about three hours to write, read, and (admittedly barely) understand a diagram to realize that this idea may be beyond the capabilities of Sinatra (and honestly beyond my current knowledge).

> "We must walk before we run."

Thus, ***The Dramatist Library*** came into existence. It is a Create Read Update Delete (CRUD), Model View Controller (MVC) app built by means of Sinatra. My goals were to ensure that I could develop an app with user authentication and host a repetoire of play descriptions while utilizing  **belongs to** and **has many** relationships. The inspiration stems from the many days spent perusing *The Drama Book Shop* in New York City. 

![Drama Book Shop](https://3.bp.blogspot.com/-V5GAOPTapZc/XL0TrgYPrzI/AAAAAAABNb0/rWlr4oyLr_MruqgbBkSCxqJSC68o0hhUQCLcBGAs/s1600/photo.jpg)

The app is intended to provide playwrights an online resource to list their material. Playwrights, or users, have the ability to create an account, login, and contribute plays to the library's collection. Playwrights also have the option to view lists of plays from other playwrights, either grouped by title or author.

### The Process

![Computer Screen](https://i.cbc.ca/1.3473565.1489087511!/fileImage/httpImage/image.jpg_gen/derivatives/16x9_780/programming-code.jpg)

In comparison to a previous CLI Data App, I took much more time to plan out code rather than diving right in. This strategy proved effective, as I was able to refine and fully understand relationships between classes (Plays and Playwrights). In my pre-coding planning, I mapped out my ***Mininum Viable Product*** (MVP) goals versus my ***stretch*** goals. Some of the goals include the following:

```
MVP: 
1. Users can create an account, login, and logout
2. Users can create, read, update, and delete plays

Stretch: 
1. Users can view list by play or playwright
2. Users can edit profiles
3. Incorporate styling with CSS
```

Using the outline above as a guide, I focused primarily on setting up the *Models*, *Views*, and *Controllers*. The initial priority was to ensure that the routes and views were established. To start, I would *stub* out a route in my controller.

```
playwright_controller.rb

get '/login' do
   "This is the login page."
end
```

Before coding further, I jumped into the browser via shotgun and to confirm that the following text appeared in the browser:

```
This is the login page.
```

Once this was successful, I routed my controller to a views page, with a simple string, to ensure that everything is running smoothly.

```
playwright_controller.rb

get '/login' do
   erb :'playwrights/login'
end

playwrights/login.erb

<p> This is the login erb file. </p>
```

I would then progress to ensure that *post*, *patch*, and *delete* routes were setup. Once the foundation was set, and the MVP goals were complete, I was then able to refactor and work towards stretch goals. Line by line, through the usage of shotgun, tux, and pry, I was able to build ***The Dramatist Library***. 

### The Reflection

While in the process of building a *Content Management System* (CMS) app through Sinatra, I kept my priorities in sight: instill and maintain functionality, then incorporate stretch goals. Code and refactor.

Through *Error Driven Development* and refactoring, it's truly possible to code and create a fluid work of art. While there is undoubtedly a technical aspect to software engineering, the artist in me is quite pleased that building an app is quite a creative feat. 

