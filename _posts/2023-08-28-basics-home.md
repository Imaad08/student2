---
layout: post
title: Web Programming Basics
description: Web Programming Basics
comments: True
categories: ['5.A', 'C4.1']
courses: {'compsci': {'week': 5}}
permalink: /basics/home
type: hacks
---

{% include nav_basics.html %}


# A guide to basic concepts in Web Notebook
- Making a menu
- Use menu to Guide topics
- Make your own custom page and menu
- Making a page dynamic through JavaScript
- Review usage of Styles in GitHub Pages

# How to import this setup into your student repository
- NOTE: To copy files between repostories, open two vscode windows and you can drag and drop
- Copy the file _includes/nav_basics.html into the _includes folder of your student repository
  - This creates the navigation between the different pages in the Web Dev Basics
- Copy the following files from _notebooks into your _notebooks folder
  - 2023-03-28-basics-home.ipynb, 2023-03-28-basics-html.ipynb, 2023-03-29-basics-of-js.ipynb, 2023-08-30-basics-of-js-data-types.ipynb, 2023-08-30-basics-js-with-html.ipynb, 2023-09-20-1_4-js-errors.ipynb
- In the basics homepage (2023-03-28-basics-home.ipynb), you need to make an edit
  - In the top cell, modify the courses to say `{ compsci: { week: 5 } }` (this will move this into your schedule page)

# Seeing javascript console output in visual studio
- When printing outputs from javascript to the console you will need to open the developer console
  - Go to Help->Toggle Developer Tools and click console on the top bar of the developer window
