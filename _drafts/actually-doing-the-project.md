---
layout: post
title: "Actually Doing the Project"
subtitle: ""
tags: [Blueprints, Unreal Engine, Level Generation]
date: 2019-02-10

excerpt: ""
references:
  - name: ""
    link: ""
---

#### This week I've actually been doing some work towards the project 🎉.

From the start I knew building a level generation system was going to be a complex and difficult task, but I did not think it would cause so many development issues as it has. I'm currently battling a bug where an array entry isn't removed, even though it should have met the criteria to be removed.

Unreal blueprint embed, caption: Anyone have any ideas?

#### So, how did I get there?

In a previous post I outlined how a prototype level generation algorithm would work. As of that post I had a system to generate a grid of coordinates. These coordinates would be used to reference items in a 2D array, or 'Map' as Unreal calls them. This week I actually continued building onto that system. The next step for this algorithm is to choose a starting cell. This is an easy task.
