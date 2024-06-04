---
layout: post
title: Streamlining DOM Manipulation
subtitle:  with ESModules in Vanilla JS
gh-repo: abstractionslimited/club-national-strapi-v4
gh-badge: [follow]
tags: [javascript]
comments: true
# mathjax: true
author: Khanya Kupelo
---

## Introduction

As someone who's recently delved into the clean architecture (more on this later), I've come to recognize the importance of using modules in projects. As a newcomer to Vanilla JS, I've found a particularly effective way of achieving this. In this blog post, I'll share my insights on using ESModules for better module management and efficient DOM manipulation.

## Understanding the Challenge

One of the key challenges I encountered was figuring out how to add events to DOM elements, such as buttons, using scripts marked as modules and those that weren't. When working with modules, it's crucial to understand how to interact with the document object to manipulate the DOM. If this sounds confusing, don't worry – the steps outlined below are simplified to help you get started.

**Step 1:**
 Set Up Your HTML Page
Start by creating your HTML page and adding a script tag with type='module'. Here's a snippet of what it might look like:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Timetable</title>
  <script src="/src/app/main.js" type="module"></script>
</head>
<body>
  <header></header>
  <div id="timetable">
    <h1>Timetable</h1>
    <button id="btn">Click me</button>
  </div>
</body>
</html>
```

**Step 2:** Initialize Your UI and Variables


Create an init function to initialize your user interface and any other critical variables. Here's an example:

```javascript

function init() {
  const button = document.getElementById('btn');
  button.addEventListener('click', () => {
    bye();
  });

  const paragraph = createElement('p');
  paragraph.innerText = 'Hello World';

  document.body.appendChild(paragraph);
}

window.onload = init;

function bye() {
  console.log('hello');
}

function getElementById(id) {
  return document.getElementById(id);
}

function createElement(tag) {
  return document.createElement(tag);
}
```

**Step 3:** Invoke Your init Function
Make sure your init function is invoked either through `window.onload` or directly using `init().`

```javascript
window.onload = init;
// Alternatively
init();

```

## Conclusion and Feedback

This blog post is the beginning of a series aimed at simplifying your journey into utilizing ESModules for DOM manipulation in Vanilla JS. I encourage you to provide feedback and ask questions as we continue exploring this topic together.

Thank you for reading, and stay tuned for the next installment!

Your feedback is valuable – feel free to share your thoughts in the comments.
