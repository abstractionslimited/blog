---
layout: post
title: Clean Architecture
subtitle:  Reuse and maintainability
gh-repo: abstractionslimited/club-national-strapi-v4
gh-badge: [follow]
tags: [javascript]
comments: true
# mathjax: true
author: Khanya Kupelo
---
## Introduction

I am currently busy building a virtual lab that will contain frontend, database connectivity, backend, and cloud infrastructure.  I want these to be presented as components and to be independent of each other.

Imagine being able to switch your front end from React JS to Svelte without having to change the code that connects to AWS or Postgres.

## Solution: Clean Architecture

- It's a way to manage interdependence between [modules](https://dev.to/abstractionslimited/streamlining-dom-manipulation-with-esmodules-in-vanilla-js-19fo)
- Combines SOLID principles and Domain-driven design
- These principles are achieved through module structuring
- Clean architecture principles remove dependence on
  - Libraries
  - infrastructure
- For example
  - I will be using this on [SMS]([https://github.com/abstractionslimited/SMS])

![The Clean Architecture](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5qn658kub6t5cvpkmesb.png)

---

### Entities/Domain

- Objects with methods and properties
- Set of data structures and functions
- Less likely to change when something external changes
- Could be used by many different applications in the enterprise

### Use Cases/Application

- contains application specific business rules/logic
- It encapsulates and implements all of the use cases of the system.
- Use cases manage (orchestrate) the flow of data to and from entities
- This layer’s changes must not affect entities
- This layer should also not be affected by changes in database, the ui or any of the common frameworks

> Its a set of instructions from executing things from start to finish using a block of code. Its like a recipe that helps the computer know what to do.
>

```javascript
// Use Case: Adding an Item to the Cart

// Step 1: User clicks on "Add to Cart" button
document
  .getElementById("add-to-cart-button")
  .addEventListener("click", function () {
    // Step 2: Get the details of the selected item
    const itemName = document.getElementById("item-name").innerText;
    const itemPrice = parseFloat(
      document.getElementById("item-price").innerText
    );

    // Step 3: Create an object to represent the item
    const newItem = {
      name: itemName,
      price: itemPrice,
      quantity: 1,
    };

    // Step 4: Add the item to the user's cart
    // This is where you would have code to manage the cart, like an array or an object

    // Step 5: Update the cart total and display
    // This is where you would update the total price and show the cart contents to the user

    // Step 6: Show a message to the user that the item was added
    alert("Item added to cart: " + itemName);
  });
```

### Interface Adapters

- Code found here is a set of adapters that convert data in Entity format to format that matches an external dependency for example Database
- This might have for example the MVC Architecture of a GUI
  - View layer responsible for rendering the UI
  - Controllers layer for routes and defining logic for those routes
  - Model layer responsible for communicating with the database

### Frameworks and drivers

- Web frameworks
- Database

## References

[Clean Coder Blog](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)

[The Software Architecture Handbook](https://www.freecodecamp.org/news/an-introduction-to-software-architecture-patterns/#what-is-software-architecture)

[Android Architecture Patterns — MVC, MVP, MVVM, MVI, Clean Architecture](https://medium.com/droidblogs/android-architecture-patterns-mvc-mvp-mvvm-mvi-clean-architecture-cde8029b8f37)

[The Clean Architecture — Beginner’s Guide](https://betterprogramming.pub/the-clean-architecture-beginners-guide-e4b7058c1165)

[Clean Node.js Architecture —With NestJS and TypeScript](https://betterprogramming.pub/clean-node-js-architecture-with-nestjs-and-typescript-34b9398d790f)

[Clean Architecture](https://yoan-thirion.gitbook.io/knowledge-base/software-craftsmanship/code-katas/clean-architecture)

[Why is Clean Architecture so Popular?](https://codeopinion.com/why-is-clean-architecture-so-popular/)

[Clean Architecture on Frontend](https://bespoyasov.me/blog/clean-architecture-on-frontend/)

<https://github.com/bespoyasov/frontend-clean-architecture>
