---
layout: post
title:      "Beginner’s Guide to Bootstrap v5.0"
date:       2021-03-10 15:47:33 -0500
permalink:  beginner_s_guide_to_bootstrap_v5_0
---


![Bootstrap with computer](https://www.tutorialrepublic.com/lib/images/bootstrap-illustration.png)

I recently created a Single Page Application (SPA) titled [Fruits Parlor Crown ](https://github.com/cglorious/fruits-parlor-crown-frontend) with Flatiron School that communicates with the [backend API](https://github.com/cglorious/fruits-parlor-crown-backend) built with Ruby on Rails. It is a Sailor Moon fandom database for characters in the Sailor Moon anime series, dividing them into the protagonist group *Guardian* and antagonist group *Villain*.

Whereas previously I implemented Vanilla CSS, my goal for this project was to utilize [Bootstrap v5.0](https://getbootstrap.com/docs/5.0/getting-started/introduction/) as a framework. Additionally, I created HTML dynamically using JavaScript.

This article serves as a beginner's guide to integrating the Bootstrap framework for the first time while programming HTML elements dynamically with JavaScript. To code along, make sure to create a project with an index.html file and index.js file.

## The Setup
Bootstrap is developed [mobile first](https://medium.com/@Vincentxia77/what-is-mobile-first-design-why-its-important-how-to-make-it-7d3cf2e29d00). In order to ensure that code renders and responds to touch zooming for all devices, add the responsive viewport meta tag to your `<head>`.

```
 <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <title>Hello, world!</title>
  </head>
```

Once this is complete, add your Bootstrap CSS stylesheet `<link>` in your `<head>` below the meta tags. At this point, the head tag includes both the *meta tags* and *Bootstrap CSS*.

```
 <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-BmbxuPwQa2lc/FVzBcNJ7UAyJxM6wuqIj61tLrc4wSX0szH/Ev+nYRRuWlolflfl" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
```

Many of the components with Bootstrap will require the use of JavaScript to function. Be sure to reference [Bootstrap documentation](https://getbootstrap.com/docs/5.0/getting-started/introduction/#js) for more details. Place one of following `<script>` tag options (listed as Option 1 and Option 2) near the end of your pages, right before the closing `</body>` tag. 

```
<body>
<!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta2/dist/js/bootstrap.bundle.min.js" integrity="sha384-b5kHyXgcpbZJO/tY9Ul7kGkf1S0CWuKcCD38l8YkeH8z8QjE0GmW1gYU5S9FOnJ0" crossorigin="anonymous"></script>

    <!-- Option 2: Separate Popper and Bootstrap JS -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.6.0/dist/umd/popper.min.js" integrity="sha384-KsvD1yqQ1/1+IA7gi3P0tyJcT3vR+NdBTt13hSJ2lnve8agRGXTTyNaBYmCR/Nwi" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta2/dist/js/bootstrap.min.js" integrity="sha384-nsg8ua9HAw1y0W1btsyWgBklPnCUAFLuTMS2G72MMONqmOymq585AcH49TLBQObG" crossorigin="anonymous"></script>
    -->
</body>
```

Again, note that the Bootstrap documentation indicates that you’ll need one of the two options. For the design of my particular SPA, I found that I needed both Option 1 and Option 2 for my SPA to function.

## Writing the Code
I found the Bootstrap documentation particularly useful when designing my web application. Since I wrote HTML dynamically using [Document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) in Javascript, I’ll be referencing both the index.html and index.js file. 

### index.html
Let’s add a [Responsive Image](https://getbootstrap.com/docs/5.0/content/images/#aligning-images) to our index.html. While we will ultimately be programming our HTML elements with Javascript, I found that writing a note in the index.html file with the intended result particularly useful.

```
<body>
<!-- image to be added using Javascript.
    <img src="https://static.remove.bg/sample-gallery/graphics/bird-thumbnail.jpg" class="rounded mx-auto d-block" alt="bird">
-->
...
</body>
```

Now that we have a reference point, it’s time to write the code dynamically in index.js.

### index.js

We’ll start by defining a function in our index.js file. 

```
function addImage(){ 
}
```

Then we’ll use [document.querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) to locate the body tag of our index.html document, and assign it to const bodyTag. We will need to append our newly created node shortly, so this will be useful for us.

```
function addImage(){ 
  const bodyTag = document.querySelector(‘body’)
}
```

Now we’re ready to replicate the img tag from index.html. We’ll start by creating the img tag with [document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) and assign it to a variable.

`const imgTag = createElement(‘img’)`

Our function now looks like this.

```
function addImage(){ 
  const bodyTag = document.querySelector(‘body’)
  const imgTag = createElement(‘img’)
}
```

Before adding [HTML attributes](https://www.w3schools.com/html/html_attributes.asp), I like to append the element. That way, we can test to make sure that elements are created and appended to the DOM.

function addImage(){ 
  const bodyTag = document.querySelector(‘body’)
  const imgTag = createElement(‘img’)
  
  bodyTag.append(‘imgTag’)
}


Our rendered page on the DOM would now have the following nodes.

```
<body>
  <img>
  ...
</body>
```

Now it’s time to replicate our Bootstrap img tag. For reference, here's what's in our index.html file.

`   <img src="https://static.remove.bg/sample-gallery/graphics/bird-thumbnail.jpg" class="rounded mx-auto d-block" alt="bird">`

We will need to add a src, class, and alt. Since the src attribute for the [<img> tag ](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) is required, and the alt is recommended, we can add this dynamically using the following.

```
imgTag.src = “https://static.remove.bg/sample-gallery/graphics/bird-thumbnail.jpg”
imgTag.alt = “bird”
```

Finally, we need to add the class attribute to our image tag. To do so, we’ll use the [Element.setAttribute( )](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute). Keep in mind that the class is the attribute that links us to the Bootstrap styles.

`imgTag.setAttribute(‘class’, ‘rounded mx-auto d-block’)`

Our completed function now looks like this:

```
function addImage(){ 
Const bodyTag = document.querySelector(‘body’)
Const imgTag = createElement(‘img’)

imgTag.src = “https://static.remove.bg/sample-gallery/graphics/bird-thumbnail.jpg”
imgTag.alt = “bird”
imgTag.setAttribute(‘class’, ‘rounded mx-auto d-block’)

bodyTag.append(‘imgTag’)
}
```

In order to make sure that our function runs, we’ll call on our function to execute once the DOM is loaded.

```
document.addEventListener('DOMContentLoaded', () => {
  addImage()
})
```

Use dev tools in the browser to inspect and make sure that the elements match `<img>` tag in our index.html file. If all is well, delete the commented out `<img>` tag on index.html. There is no need for this tag since we have added HTML dynamically using Javascript.

Happy coding!

![Computer with Code](https://miro.medium.com/max/7086/1*ijXZHH03A0aQih33x8h6Rg.jpeg)


	 
	 


