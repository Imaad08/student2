---
toc: false
comments: true
layout: post
title: Review Ticket
description: Spotify playlist on my website
courses: { compsci: {week: 5} }
type: hacks
---
# Week 5 Review Ticket: HTML Basics and JavaScript Fundamentals

In this review, we will cover essential concepts related to HTML and JavaScript fundamentals.

## HTML Basics

HTML, which stands for HyperText Markup Language, is the backbone of web development. It uses opening and closing tags to structure content. Key HTML elements include:

- Paragraph: `<p></p>`
- Link: `<a href="https://www.w3schools.com/html/default.asp">Visit W3Schools HTML Page</a>`
- Image: `<img alt="describe image" src="link to image" width="100" height="200">`
- Bold text: `<strong>Bolded Text</strong>`
- Italics: `<i>Italic Text</i>`
- Button: `<button>some button text</button>`

## JavaScript Data Types

JavaScript, a versatile programming language, offers various data types:

- **String Data Type:** Used for storing text. You can perform string manipulation using functions like `toUpperCase()`, `toLowerCase()`, and `substring()`.
- **Number Data Type:** For storing numerical values. You can perform mathematical operations and formatting.
- **Array Data Type:** Lists used to store multiple values. You can access array elements by their index and use functions like `push()` and `pop()`.
- **Object Data Type:** Objects store data as key-value pairs, enabling you to create structured data. Considerations include object literals and constructor functions.

## Using JavaScript with HTML DOM

Working with the Document Object Model (DOM) allows you to interact with HTML elements dynamically. Some key points:

- **Workspace Update:** Always run `git pull` to stay updated in a collaborative coding environment.
- **Referencing HTML Elements:** Use `document.getElementById("idTag")` to reference elements by their unique IDs. The `.innerHTML` attribute allows access and modification of content within tags.
- **Element Creation & Insertion:** Use `document.createElement(type)` to create elements programmatically. The `.appendChild(element)` method adds elements to the HTML structure.
- **Utilizing Functions:** Functions are essential for code organization and reusability. They can take parameters and return values. Events, such as button clicks, can trigger these functions.

## Basics of JavaScript

JavaScript is commonly used for adding interactivity to web pages. Some foundational concepts:

- **Embedding JavaScript:** You can embed JavaScript within HTML using the `<script>` tag or in Jupyter cells using the `%%html` magic command.
- **Console Logging:** Use `console.log()` to print messages to the browser's console. You can access the console through the browser's developer tools.
- **Data Storage & Types:** JavaScript provides basic data types like strings, numbers, and booleans. You declare variables using `var`, `let`, or `const`.
- **Data Access & Manipulation:** Access and manipulate data by referencing variable names. For strings, you can use operators like `+` for concatenation.
- **Number Operations:** Perform arithmetic operations and comparisons. Use `==` for value comparison and `===` for type and value comparison.
- **Conditional Statements:** Use `if-else` statements for conditional execution of code blocks. Combine with operators for dynamic comparisons and responses.

## JavaScript Errors

Let's review and improve code segments to address common issues:

### Segment 1: Alphabet List

**Intended Behavior:** Create a list of characters from the string contained in the variable `alphabet`.

**What I Changed:** The `for` loop’s condition should be `i < alphabet.length` to iterate over each character in `alphabet`. Instead of pushing `i`, which is a number, push `alphabet[i]` to add each character to `alphabetList`.

### Segment 2: Numbered Alphabet

**Intended Behavior:** Print the number and corresponding character in `alphabet` based on `letterNumber`.

**What I Changed:** Adjusted the loop’s condition and corrected the `console.log` statement for accurate output.

### Segment 3: Odd Numbers

**Intended Behavior:** Print all odd numbers below 10.

**What I Changed:** Adjusted the initialization and incrementation of `i` to produce odd numbers correctly.

### Challenge Segment: Cost Calculator

**Goal:** Error-proof the code and implement a user input test.

**What to Do:** Develop tests for user inputs and expected outputs. Gradually implement features to pass these tests. Iterate until the program functions as expected.

This review ticket serves as a reference for understanding HTML basics, JavaScript data types, DOM manipulation, and common code debugging practices. Happy coding!
