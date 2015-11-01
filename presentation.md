# Building Of Modern Application

---

# Single Page Application

> SPA

---

# Traditional Web Application

> Hard way

---

![Hard way](http://nerds.airbnb.com/wp-content/uploads/2012/10/shared-js-app.png.scaled500.png)

---

### 1. run seamlessly both client and server
### 2. logic and view rendering can run on the server (Perf, SEO)
### 3. logic and view rendering can run on the client (UX/UI)

---

# A Static Web Application

> Easy way

---

![Easy Way](http://nerds.airbnb.com/wp-content/uploads/2012/10/client-js-app.png.scaled500.png)

---

## 1. run almost entirely in Browser
## 2. server for static files and API

---

# Hybrids Apps

> advantages of both static and traditional apps

---

# many architectural challenges

> Ready?

---

# Broad Appel

> HTML, JavaScript, and CSS only

---

# Rapid development

> sketch out with frameworks

---

# Simple Scalability

> Just stored files.
> Backend from vendors

---

# Modularity

> Separation of concerns

---

# Increased Flexibility

> simpler when the back-end and the front-end are built independently

---

# Thinking With Services

> Service-Oriented Architecture (SOA)

---

### 1. Use technologies that fits your needs
### 2. Clean boundaries between services
### 3. Third parties

> User Interface Service

---

# Time to assemble

![lego](http://blog.ippon.fr/wp-content/uploads/2015/03/lego-189762_1280.jpg)

---

# CSS Preprocessor Languages

> Programming language that are compiled into CSS

---

# SASS

> Syntactically Awesome Style Sheets

---

### what Sass really offers?

# whatever css doesn’t… yet

---

* Variables
* Nesting
* Partials
* Mixins
* Inheritance
* Operators
* Control Directives
* Functions

---

# Variables

```css
$color-primary: #3385FF;
$heading-padding: 10px;

h1{
  color: $color-primary;
  padding: $heading-padding;
}
```

---

# Nesting

```css
nav {

  & > ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li {
    display: inline-block;

    & > a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;

    }
  }
}
```

---

# Partials

```css
@import "foundation/components/block-grid",
"foundation/components/buttons",
"foundation/components/forms",
"foundation/components/grid",
"my-scss/my-typography",
"my-scss/my-branding",
"my-scss/my-buttons";
```

---

# Inheritance

```css
.alert {
  border: 1px solid #555;
  padding: 10px;
  color: #333;
}

.alert-success {
  @extend .alert;
  border-color: green;
}

.alert-danger {
  @extend .alert;
  border-color: red;
}

.alert-warning {
  @extend .alert;
  border-color: yellow;
}
```

---

# Tasks tools and generator

> Work smarter, not harder.

---

# Grunt or Gulp

> Automatisation

---

1. Clean any existing build [grunt-contrib-clean]
2. Compile SASS [grunt-contrib-sass]
3. Uglify and concat [grunt-contrib-uglify]
4. Copy sources to new folder [grunt-contrib-copy]

...

---

# Gulp

![gulp](https://cdn-images-2.medium.com/max/800/1*dKUA6oVXOrR9IdU1d8CfdA.png)

---

## Streams
## Vinyl
## Vinyl Adapters
## Orchestrator

---

# Yeoman

![yeoman](http://yeoman.io/static/illustration-home-inverted.1f863f34ba.png)

---

## [scaffolds] YO
## [build] GRUNT or GULP
## [manage] NPM or BOWER

---

# Package Manage

> easily install open source or shared library code

---

# NPM

---

```sh
❯ npm init
❯ npm install --save my-package    
❯ npm install -g my-package  
❯ npm publish  
```

---

# UI Frameworks

> rapid prototyping

---

* ## Foundation
* ## Bootstrap
* ## MDL

---

# Static Web Hosts

---

# JavaScript Frameworks

---

# The End of the Monolithic JavaScript Framework

---

# More UI but spaghetti code

---

# MVC

> Model-View-Controller, strict separation of concerns

---

## View logic
# VS
## Business logic

---

# Your Choice is Your Future

> a common language and a more organized workspace

---

# Most popular

---

# angularjs

![angular](https://cdn-images-2.medium.com/max/800/1*VpHTWMLGA1kAT26BXm3MFQ.png)

---

# ember

![ember](http://vfsvp.fr/images/ember/emberjs-logo.png)

---

# backbone

![backbone](https://cdn-images-2.medium.com/max/800/1*82xY2X54CAjkxFf72JPjFw.png)

---

# react



---

# Backbone

* very minimalistic
* great documentation
* code is simple: 1 hour enough

---

Backbone.Events

```js
var o = {}
_.extend(o, Backbone.Events)

o.on('zap', function () {
  console.log('zapped')
})

o.trigger('zap')
//=> outputs 'zapped'
```

---

* Backbone.Model
* Backbone.Collection

```js
// Create a new model by passing in some data
var person = new Backbone.Model({ name: 'Bob', age: '30' })

// Access the data
person.get('name')
//-> returns 'Bob'

// Observe the data for changes
// using the event methods that
// the model has inherited
person.on('change', function () {
  console.log('Something about this person changed')
})

// Mutate the data
person.set('name', 'Robert')
//-> outputs 'Something about this person changed'
```

---

Backbone.View

```js
var AppView = Backbone.View.extend({
  // el - stands for element. Every view has a element associate in with HTML
  //      content will be rendered.
  el: '#container',
  events: {
    'click button#add': 'addItem'
  },
  // It's the first function called when this view it's instantiated.
  initialize: function(){
    this.render();
  },
  // $el - it's a cached jQuery object (el), in which you can use jQuery functions
  //       to push content. Like the Hello World in this case.
  render: function(){
    this.$el.html("Hello World");
  },
  addItem: function(){
   this.counter++;
   $('ul', this.el).append("<li>hello world"+this.counter+"</li>");
  }
});

```

---

# STOP

---

# My opinion

> Building a zero framework app

---

## Corporate
## Maintainability and roadmap
## Over abstraction
## Not a clearly separation of concerns
## No dependencies

---

# Micro-libraries

> helper libraries

---

# date

> moment.js

```js
moment().format('MMMM Do YYYY, h:mm:ss a'); // November 1st 2015, 10:57:51 pm
moment().subtract(10, 'days').calendar(); // 10/22/2015
moment().endOf('day').fromNow();          // in an hour
```

---

# routing

> page.js

```js
page('/', index)
page('/user/:user', show)
page('/user/:user/edit', edit)
page('/user/:user/album', album)
page('/user/:user/album/sort', sort)
page('*', notfound)
page()
```

---

# request

> qwest

```js
qwest.post('example.com', {
  firstname: 'Pedro',
  lastname: 'Sanchez',
  age: 30
})
.then(function(xhr, response) {
  // Make some useful actions
})
.catch(function(xhr, response, e) {
  // Process the error
});
```

---

# 4 questions

> you can ask when choosing a library

---

## 1. How maintainable will this project be?

---

## 2. Do any of the individual components adversely affect performance?

---

## 3. Do any of the components adversely affect accessibility?

---

## 4. How open are the developer(s) of the components to code contributions?

---

# Wait a minute

> focus on the concept of flux

---

# Flux

> Idea for organizing app at Facebook

---

# Data moves in one direction through your application.

---

![shark](https://cdn-images-2.medium.com/max/800/1*fZkvBieSa4UE9khPDjwteQ.jpeg)

---

# Yes

> for dynamic data

# No

> for static views

---

# why focus on flux?

> Big problem in frontend development

---

# How to structure ?

> Micro-lib, AngularJS, jQuery, but Yassine said...

---

# One way data flow

* Just use the Flux Dispatcher by Facebool
* Any event library

---

# 1. Views "Dispatch" "Actions"

---

Global dispatcher

```js
var AppDispatcher = new Dispatcher();  
```

```js
<button onClick={ this.createNewItem }>New Item</button>  
```

---

Dispatch specific event

```js
createNewItem: function(evt) {
  AppDispatcher.dispatch({
      eventName: 'new-item',
      newItem: { name: 'Yass' } // example data
  });
}
```

---

# 2. Store responds to the dispatch event

---

```js
var ListStore = …

AppDispatcher.register( function( payload ) {
  switch( payload.eventName ) {
    case 'new-item':
      // We get to mutate data!
      ListStore.items.push( payload.newItem );
      break;
  }
  return true; // Needed for Flux promise resolution
});
```

---

# 3. Store emits a "Change" event

---

```js
switch( payload.eventName ) {
  case 'new-item':
    // We get to mutate data!
    ListStore.items.push( payload.newItem );

    // Tell the world we changed!
    ListStore.trigger( 'change' );
    break;
}
```

---

# 4. View Responds to the "Change" Event

```js
...
ListStore.bind( 'change', this.listChanged );
...
listChanged: function() {  
  // Since the list changed, trigger a new render.
  this.render();
}
```

```js
render: function() {
  // Remember, ListStore is global!
  // There's no need to pass it around
  var items = ListStore.getAll();

  // Build list items markup by looping
  // over the entire list
  var itemHtml = items.map( function( listItem ) {
    // Parse listItem to update template
  });
}
```

---

# Nice ?

---

# we're re-rendering the entire view !?!!

---

# React

> Facebook view layer

> React will only update the real DOM if your rendered output has changed.

---

## virtual DOM
## if diff then update real DOM

---

# And that's all ?

---

## template language
## hooks to output HTML

---

# Should I Use React?

> Componentized UI is the future of web development, and you need to start doing it now.

---

# Performance

> Need for Speed

---

# The perceived performance

> More important than true speed

---

# The user has little patience

> If they have to wait too long for content to load, they are unlikely to stick around.

---

# Basic concepts

---

### objective time or clock time
### psychological time or brain time

---

![time](https://media-mediatemple.netdna-ssl.com/wp-content/uploads/2015/09/02-perception-opt-small.png)

---

# Remember That Time Is Money

>  the fastest site experientially > the fastest site mathematically

---

## 1. Making a sale
## 2. Losing a customer

---

# only 3 seconds
### for a visitor to abandon a website

---

## how fast a user thinks your website is ?

>  Make your websites feel faster

---

# The biggest bottlenecks

> waiting for new content to load or an operation to complet

---

* ### 0–100ms - Instant
* ### 100–300ms - Small perceptible delay
* ### 300–1000ms - Machine is working
* ### 1000+ms - Likely mental context switch
* ### 10,000+ms - Task is abandoned

---

![timeline](https://media-mediatemple.netdna-ssl.com/wp-content/uploads/2015/09/05-time-spans-opt.png)

---

# 0.1 seconds

> feel instantaneous (Gold standard)

---

# 1 second

> feel the pause

---

# 10 seconds

> Struggle to maintain the user’s attention.
> Give up the website

---

# Platform success model

> from Google

---

![success](https://media-mediatemple.netdna-ssl.com/wp-content/uploads/2015/09/04-success_model-opt.png)


---

# Human to Human

* The loading page should happen immedialely
* Users should get feedback from a given action instantly

---

# 20% rules


> to see a difference, it has to be changed by a minimum of 20%

---

![jnd](https://media-mediatemple.netdna-ssl.com/wp-content/uploads/2015/09/09-clock-opt-small.png)

---

# Illusion

> show the user that something is happening

---

# Loading dialogs

---

![facebook](https://pbs.twimg.com/media/BfV93RPCMAAc1nw.jpg)

---

# Progress bar

> realtime feedback

---

![progress](http://blog.teamtreehouse.com/wp-content/uploads/2014/04/loading.gif)

---

# Loading animations

>  keep user’s attention occupied.

---

![anim](http://blog.teamtreehouse.com/wp-content/uploads/2014/04/loading-animation-demo.gif)

---

# Buttons states

### focuses
### hovered
### pressed

---

![state](http://blog.teamtreehouse.com/wp-content/uploads/2014/04/button-states.gif)

---

# Momentum Scrolling

> feel native

---

![noscroll](http://www.mobify.com/static/blog/2013/09/nooverflowscroll.gif)

---

![scroll](http://www.mobify.com/static/blog/2013/09/overflowscroll.gif)

---

# Instagram

---

### 1. starts uploading in the background
### 2. serveral steps: scale, crop, filters...

> user was distracted by going through a series of steps while the photo was being uploaded

---

![insta](https://cdn-images-2.medium.com/max/600/1*W_JPzbhrHHYxBRy8XJA5_Q.png)

---

# Whatsapp

---

![whatsapp](https://cdn-images-2.medium.com/max/600/1*-FyGAdSZNCgVwaCLFnLplA.png)

---

### 1. green checkmark for sent message
### 2. green checkmark for received message

> Even not have been fully

---

# iMessage

---

![imessage](https://cdn-images-2.medium.com/max/600/1*wQ0auiAEIS0JBGUGxze5fQ.png)

---

### Slower iMessage VS Faster Whatsapp

>  probably take around the same approximate time

---

# Skeleton

---

![FB](https://cdn-images-2.medium.com/max/600/1*hSYfv3vUEdZT3s8n7nyY-w.png)

---

![pinterest](https://cdn-images-2.medium.com/max/600/1*NULhhhLtw9nz3RhmbkR2Bw.png)

---

# Source code optimization

---

# Web storage VS cookies

```js
if (('localStorage' in window) && window.localStorage !== null) {
  // easy object property API
  localStorage.setItem('settings', ['full', 'fr'];
}
```

---

# CSS Transitions

```js
div.box {
  left: 40px;
  -webkit-transition: all 0.3s ease-out;
     -moz-transition: all 0.3s ease-out;
       -o-transition: all 0.3s ease-out;
          transition: all 0.3s ease-out;
}
div.box.totheleft { left: 0px; }
div.box.totheright { left: 80px; }
```

---

# Local database as indexdb

> persistence, offline and large

---

### 1. styles at the top
### 2. scripts at the bottom

---

# Fewer requests

>  each request is a potentially very expensive operation

---

# multiple domains

> assets from different domains

---

# Files manipulation

> concat, minify, sprite, optimize images, gzip, serve from CDN... etc

---

# 3 Musketeers

---

# RDD
# CDD
# TDD

---

# README DRIVEN DEVELOPMENT

> Right documentation first

---

[pageres](https://github.com/sindresorhus/pageres)

---

[httpie](https://github.com/jkbrzt/httpie)

---

[joe](https://github.com/karan/joe)

---

# Comment driven development


> comment programming

---

## 1. prototyping
## 2. explaining what needs for others
## 3. commenting the code

---

```js
// Get the needed models
// Collect todo items
// Get lists that the todo items belong to
// Send to View
```

---

```js
// Get the needed models
var todoTable = new TodoTable();
var listTable = new ListTable();

// Collect todo items
var todos = todoTable.get('me');

// Get lists that the todo items belong to
for (...) {
  ...
}

// Send to View
render();
```

---

# test driven development

> Write Tests First

---

# Why ?

---

## 1. Design aid
## 2. Feature documentation
## 3. Test your developer understanding
## 4. QA
## 5. Continuous Delivery

---

# Science of TDD

---

## 1. reduce bug density
## 2. encourage more modular design
## 3. reduce code complexity

---

# Mocha

---

```js
// cow.js

"use strict";

module.exports = function Student (name) {
  this.name = name || "Yassine";
}


Student.prototype = {
  sleep: function(when) {
    if (!target)
      throw new Error("missing target");
    return this.name + " sleeps " + target;
  }
};
```

---

```js
describe('Student', function() {
  describe('constructor', function() {
    it('should have a default name', function() {
      var student = new Student();
      assert(student.name === 'Yassine', 'not setting a default name');
    });

    it("should set Student's name if provided", function() {
      var student = new Student('Paul');
      assert(student.name === 'Paul', 'not setting the provided name');
    });
  });
});
```
