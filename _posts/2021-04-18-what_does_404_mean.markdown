---
layout: post
title:      "What does 404 mean?"
date:       2021-04-18 18:50:36 +0000
permalink:  what_does_404_mean
---

![404 Not Found: cat hiding underneath tissues and paper](https://i.kym-cdn.com/photos/images/newsfeed/000/236/756/b33.jpg)

If you are a user of the internet, I'm sure you've stumbled across the dreaded 404 Not Found status at least once in your user experience. If you're curious like me, you may be wondering...

What does *actually* 404 mean?

### HTTP Response Status Codes

![HTTP Status Codes image](https://miro.medium.com/max/920/1*w_iicbG7L3xEQTArjHUS6g.jpeg)

To start, let's talk about what HTTP response status codes are. As explained by [Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status), "HTTP response status codes  indicate whether a specific HTTP request has been successfully completed." They are grouped in the following categories:

1. Informational responses (100 - 199)
2. Successful responses (200 - 299)
3. Redirects (300 - 399)
4. Client errors (400 - 499)
5. Server errors (500 - 599)

For today, we'll focus on the 404 Not Found error code. 

### 404 Not Found

![404 Oops nothing to see here: Ghost with flashlight](https://www.impactplus.com/hubfs/404-error-page-examples-best.jpg)

A [404 Not Found](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/404) is an an error page, classified under the [Client Errors](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#client_error_responses) category above, are also known as a "Page Not Found" page. It's the place where users try to access a URL that doesn't exist. 

It is an inevitable part of the web.

There are a couple of reasons why a use may come across a 404 status.

**They typed in an incorrect URL**

A user could have misspelled something when they are trying to guess where a page might be.

**They followed an external link on another site that no longer works**

* A page could have been incorrectly linked on another site. 
* Alternatively, if a page was moved to another URL but the link from another site was updated, this could result in a 404 status
* The page was deleted and not longer exists

**They clicked a broken internal link on your own website**

An internal link on your own website was broken

Now that we have an idea of what 404 Not Found error codes are and how a user comes across them, let's chat briefly about ways to include them into your website. The following instructions assume you have a basic understanding of React.

### Add a 404 Page

I built React Redux application [Magic Mouse](https://github.com/cglorious/magic-mouse-frontend) with Flatiron School. The application is intended to be a ride and attraction tracker in which guests at the Disney parks can log the number of times they rode an attraction, which adds to their overall trip points.

Within the application, I implemented adding routes to render varying components depending on the user's interaction. I implemented a redirect to a 404 Not Found page as a strategy to adhere to user or potential website errors. 

##### The Setup

To implement multiple page to my app, the first step was to install the Browser version of React Router, or react-router.

`npm install react-router-dom --save`

The next step was to add the following to my App.js file.

`import { BrowserRouter as Router, Route, Switch, Redirect } from "react-router-dom";`

##### Presentational Components

At the start, I had an initial ***MainPage*** component as well as a ***NotFoundPage*** component. To start, I imported the following to the ***App.js*** file.

```
import React, { Component } from "react";
import { BrowserRouter as Router, Route, Switch, Redirect } from "react-router-dom";
import MainPage from "./components/MainPage"
import NotFoundPage from "./components/NotFoundPage";
```

##### App.js

Utilizing boilerplate structure of a class component, my ***App*** component now looked like this.

```
import React, { Component } from "react";
import { BrowserRouter as Router, Route, Switch, Redirect } from "react-router-dom";
import MainPage from "./components/MainPage"
import NotFoundPage from "./components/NotFoundPage";

class App extends Component {`
render() {
    return (
      <div>
			   App
      </div>
    );
  }

```
In order to ensure that the paths to the ***MainPage*** and the ***NotFoundPage*** components would render, I included the following:

```
import React, { Component } from "react";
import { BrowserRouter as Router, Route, Switch, Redirect } from "react-router-dom";
import MainPage from "./components/MainPage"
import NotFoundPage from "./components/NotFoundPage";

class App extends Component {`
render() {
    return (
      <div>
        <Router>
            <Route exact path='/' render={() => <MainPage />} />
						<Route exact path='/404' render={() => <NotFoundPage />} />
        </Router>
      </div>
    );
  }

```

Lastly, wrapping the Routes in a ***Switch*** component handles redirects to the ***NotFoundPage***, or 404 page.

```
import React, { Component } from "react";
import { BrowserRouter as Router, Route, Switch, Redirect } from "react-router-dom";
import MainPage from "./components/MainPage"
import NotFoundPage from "./components/NotFoundPage";

class App extends Component {`
render() {
    return (
      <div>
        <NavBar />
        <Router>
          <Switch>
              <Route exact path='/' render={() => <MainPage />} />
						  <Route exact path='/404' render={() => <NotFoundPage />} />
						  <Redirect to='/404' />
            </Switch>
        </Router>
      </div>
    );
  }
```
If a user inputs an incorrect url, or if there is a broken link within the website, a user will be redirected to this 404 page.

### You Will Be Found

![Image from Dear Evan Hansen the musical](https://broadwaydirect.com/wp-content/uploads/2018/05/1200x450_DEH_BroadwayDirectTakeover5.18_0840_FeaturedStory2-800x450.jpg)

In the event that a user comes across a 404 Error Code, don't fret! Construct your 404 Not Found pages in a way that the user feels that they will find there way again. Constructing these 404 pages in a way that such as leads users to a relevant part of the website, like a homepage or relevant content, will ensure that you maximize the user's overall enjoyable experience. 

I leave you with a few well constructed 404 Not Found pages.

* [Amazon](https://www.amazon.com/afghbafan)
* [Conductor](https://www.conductor.com/aofhwaufa)
* [Magnt](https://www.magnt.com/asdfasd)
