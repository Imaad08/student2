---
comments: true
layout: post
title: Individual Review - Tri 2
description: Individual Review - Tri 2
type: tangibles
courses: { compsci: { week: 3 } }
---

# The Project:

After looking at college board requirements, our group decided to make a meme creator. Users can upload images with top and bottom text and the option to add the image to a public database. Users can also download other users memes from the database.

# My Feature:

I created the meme editor python logic where the user can upload an image and add text to the top and bottom of the image and optionally add to the database. This is done by using the PIL library and functions to convert between base64 data and images.

# CPT Review

| Collegeboard Requirements                                                                                                                                                      | Feature Included in the project                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Instructions for input from one of the following: the user, a device, an online datas stream, a file.                                                                          | The project takes image and text input from the user to send to the backend. <img src="https://i.ibb.co/yF69vQd/SCR-20240225-qtvk.png">                                                                    |
| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the users purpose. | The meme images are stored in a Sqlite table that other users can access and download from using the JSON data stored in the table. <img src="https://i.ibb.co/Y0z5BxG/SCR-20240225-qvfa.png" width="800"> |
| At least one procedure that contirubted to the program's intened purpose where you have defined: the name, return type, one or more parameters:                                | After creating the meme, the image is returned. <img src="https://i.ibb.co/DfXpkBt/SCR-20240225-qyjb.png">                                                                                                 |
| An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure                                                                  | This is an if function to determine wether or not the image will be added to the database based on user input. <img src="https://i.ibb.co/h1c0n12/SCR-20240225-rcui.png" alt="SCR-20240225-rcui">          |
| Calls to your student-developed prodcedure                                                                                                                                     | <img src="https://i.ibb.co/DfXpkBt/SCR-20240225-qyjb.png">                                                                                                                                                 |
| Instructions for output (tactile, audible, visual, or ) based on input and program functionality                                                                               | This is the javascript that sends the image and top and bottom text and then returns the meme image. <img src="https://i.ibb.co/CJGBkVB/SCR-20240225-rasc.png">                                            |

# Video

[Link](https://drive.google.com/file/d/1dgTAOWLZUIqucgQBTbtfKY3E8AQJrTWB/view?usp=sharing)

| Collegboard Requirements                                 | Video                                         |
| -------------------------------------------------------- | --------------------------------------------- |
| Input                                                    | Image, top text, bottom text, add to database |
| At least one aspect of the functionality of your program | Meme creation with PIL                        |
| Output                                                   | Completed meme being shown as result          |

<script src="https://utteranc.es/client.js"
        repo="imaad08/student2"
        issue-term="pathname"
        theme="github-dark"
        crossorigin="anonymous"
        async>
</script>
