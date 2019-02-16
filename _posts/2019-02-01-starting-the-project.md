---
layout: post
title: "Starting the Project"
subtitle: "Oh great, now I'm nervous."
tags: [GitHub, Project Management, Web Development]
date: 2019-02-01
references:
  - name: "The Drunkard Walk Algorithm"
    link: "http://pcg.wikidot.com/pcg-algorithm:drunkard-walk"
  - name: GitHub
    link: "https://github.com"
---

Before starting the second semester I already began prototyping ideas for the project. Particularly I looked into how procedurally generated levels would work in Unreal Engine 4 using blueprints.

The first prototype I developed used [The Drunkard Walk Algorithm](http://pcg.wikidot.com/pcg-algorithm:drunkard-walk). So called because of the random, staggery patterns the algorithm can create.
In this algorithm a grid is generated and a random cell in that grid. That cell is assigned as a room, and a new cardinal direction is chosen (North, South, East or West). The script then checks if it can move to that cell. If it can, it moves to the cell in that direction and places a new room. This process is repeated as many times as the number of rooms you want to generate. In my project, I had rooms with multiple doors and ran the algorithm on each room generated for each door.

I had this working for the most part, but I realised that there were some issues that could occur later in development. Namely, I struggled to figure out a way of doing the appropriate checks to see if a room would be a valid space. There was also an issue where the room generation would tend to spread out like a tree, forming unnatural feeling dungeons.

Due to these reasons, I retooled the algorithm. In the second version the dungeon is entirely data driven; no rooms are generated until after all the checks have been validated. This improved the dungeon generation algorithm considerably. Data driven dungeon generation has the benefit of being able to do checks using maths, rather than world coordinates. This is the algorithm I will be sticking with for this project. It is somewhat more complex as it does not actually exist while it builds itself. But the benefits it brings far outweigh the added complexity.

#### Project management. Or rather, my ability to overcomplicate trivial tasks for the sake of "Because I wanted to."

I made the decision to have everything hosted on [GitHub](https://github.com). I wanted to keep all my information in one location. This was basically for my own sanity, but it will make finding information easier. When choosing to do that though, I did not take in to account having to make a blog. And to be honest, this could have easily been put elsewhere and it would not have made organisation more difficult. I was given the ability to build my blog directly into and I took it. If nothing else, this is a fun side project for me to work on during the main project.
