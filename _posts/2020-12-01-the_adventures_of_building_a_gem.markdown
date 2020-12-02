---
layout: post
title:      "The Adventures of Building A Gem"
date:       2020-12-02 03:17:27 +0000
permalink:  the_adventures_of_building_a_gem
---

### Failures and Errors

Admittedly, I am a Type-A type of person. It has been a blessing in some ways. But while learning to code, there has been quite a bit of unlearning to do. I had to succumb to the thought that something in your code will most likely go wrong. Your code will probably break more often than not. There will be times when you just don't get it. 

While diving into the Flatiron curriculum, and *especially* while creating my first CLI Data Gem project with Flatiron School, I learned how to fail, **a lot**. And also, I'm learning to be okay with failure. Failure isn't a bad thing - it's part of growth!

Failures, by means of errors in code, are opportunities for refactoring... and ultimately **growth**.

### Dubnation

![Curry](https://api.time.com/wp-content/uploads/2019/06/golden-state-warriors.jpg?w=800&quality=85)

The CLI Data Gem project I created is based on the Golden State Warriors. It is a Warriors coach app, in which the user acts as a Warriors coach that decides which players will be in the starting lineup based on information from the [Warriors Roster](https://www.nba.com/warriors/roster). The user has the opportunity to view player's information to make the best decision for the starting lineup of five. 

I chose this project because:

1. I love basketball.
2. I am part of the [Dubnation](https://www.urbandictionary.com/define.php?term=Dubnation).

Once I got my code to a satisfactory working mode, I stumbled across an error. Initially, when I started writing my code, there were 13 players on the Warriors roster. To account for this, I hard-coded the following:

```
puts "Choose an option between 1 and 13."
```

Hard coding this was fine for a bit. But guess what happened... *The NBA Draft, that's what!* As I built my code, the number of players on the roster would change based on the draft picks. For instance, the Warriors roster could start at 19 on one day, and change to 21 the next! 

*Yikes!* 

But also... **hooray!** An opportunity for growth! I knew that this was my chance to make my code more flexible.

### Refactoring

First, I first stubbed out what I needed to happen.

```
# puts "Choose an option between 1 and (the total number of players)."
```

Where could I find the total number of players? Right - the @players array!

```
@players = [ ]
```

In order to get the total number of players, I called the array class method *.length*.

```
@players.length
```

I then used string interpolation, and replaced 13 with:

```
#{@players.length}
```

And finally:

```
puts "Choose an option between 1 and #{@players.length}."
```

By doing so, this allowed my code to become much more flexible. And the good news is, I'm able to stay up to date on NBA trades while refactoring and debugging. A win for all!

### Adjusting to a Growth Mindset

I find it amusing when software engineers exclaim *cool!* or *great!* upon reading errors. I wouldn't say I'm excited at seeing errors, but I do find myself having a bit more patience the more I code. 

Rather than dwell in the failures and let that scary error message take over, I remind myself that it's part of the process. Growth mindset is a real thing. Rather than an *I don't know it,* try an **I don't know it... yet**. The knowledge will come. 

>“In a growth mindset, people believe that their most basic abilities can be developed through dedication and hard work—brains and talent are just the starting point. This view creates a love of learning and a resilience that is essential for great accomplishment.” ( Dweck, 2015)
