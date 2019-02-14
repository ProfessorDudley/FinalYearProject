---
layout: post
title: "Actually Doing the Project"
subtitle: "I mean, I probably should right? Right??"
tags: [Blueprints, Unreal Engine, Level Generation]
date: 2019-02-10

excerpt: "From the start I knew building a level generation system was going to be a complex and difficult task, but I did not think it would cause so many development issues as it has. I'm currently battling a bug where an array entry isn't removed, even though it should have met the criteria to be removed."
---

#### This week I've actually been doing some work towards the project. 🎉

From the start I knew building a level generation system was going to be a complex and difficult task, but I did not think it would cause so many development issues as it has. I'm currently battling a bug where an array entry isn't removed, even though it should have met the criteria to be removed.

<div class="embed">
<div class="iframe-container">
<iframe src="https://blueprintue.com/render/ctxfm0zq" scrolling="no"></iframe>
</div>
<h5>Anyone have any ideas?</h5>
</div>

#### So, how did I get there?

In a previous post I outlined how a prototype level generation algorithm would work. As of that post I had a system to generate a grid of coordinates. These coordinates would be used to reference items in a 2D array, or 'Map' as Unreal calls them. This week I actually continued building onto that system. The next step for this algorithm is to choose a starting cell. This is an easy task. Just get a random key from the level grid map and set that to be the starting cell.

#### That was the easy part; now it gets complicated.

Now that we have a starting cell, we can begin the drunken man algorithm and assigning rooms to cells. This requires finding out the states of the adjacent cells. We can use this information to determine which room needs to be generated on the current cell. The logic for checking this is actually quite simple, but it is complex to execute.

<div class="embed">
<div class="iframe-container">
<iframe src="https://blueprintue.com/render/9_mwcoph" scrolling="no"></iframe>
</div>
<h5>This mess checks adjacent cells in a grid and uses that to determine if a direction is valid. Trust me, this works flawlessly.</h5>
</div>

Put simply:
- For any given direction around the current cell:
  - If the adjacent cell would be off the grid, mark that direction as **INVALID**
  - If the adjacent cell does not contain a room, mark that direction as **OPTIONAL**.
  - If the adjacent cell is a room:
    - If it has a door leading back to our room, mark that direction as **NECESSARY**.
    - If it does not have a door leading back to our room, mark that direction as **INVALID**.

All of these values are outputted as a Map where the directions are keys, and their status is its value.

This took some time to implement and get working, but it is a fairly simple construct. The next step to work on is using these values to determine which room should be spawned.
