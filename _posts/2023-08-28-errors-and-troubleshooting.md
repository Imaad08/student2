---
layout: post
title: Errors and Troubleshooting
description: Issues I encountered and how I got past them.
toc: True
comments: True
categories: ['5.A', 'C4.1']
courses: {'csse': {'week': 1}, 'csp': {'week': 1, 'categories': ['6.B']}, 'csa': {'week': 1}}
type: devops
---

## Errors I encountered and how I fixed them

- Encountered error with Ruby version after downloading Ruby 3 via Homebrew.
Command ruby -v showed version 2.6 (default macOS version), causing issues with some Ruby commands.

- Used which -a ruby to identify incorrect Ruby directory in terminal.
Installed Jekyll gems after correcting Ruby directory.

- Ran brew info ruby to gather information from terminal output.
Echo command from output set correct Ruby directory.

- Faced Python version and pip command issue.
pip commands not detected, python --version showed 2.7 despite installing version 3.11.4.

- Followed guidance from Mr. Mortensen, ran activate_macos.sh script to fix Python and pip issue.

- Successful in obtaining correct Python version and getting pip commands to work.

- Ran bundle install and make to begin editing website.

- Identified code issue: Overlapping text in minimal theme's blog section (config.yml file).

- Suspected styling error in header tag causing the problem.

- Unable to locate exact error in styling.

- Recent error in styling calculator: Added style.css but text displayed under buttons.

- Resolved by merging CSS and JavaScript into markdown using style and script tags.

