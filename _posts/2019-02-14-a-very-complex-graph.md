---
layout: post
title: "A Very Complex Graph"
subtitle: "Thank you Neil for fixing literally everything."
tags: [Blueprints, Unreal Engine, Level Generation]
date: 2019-02-14

excerpt: "I've spent the past week working on this nightmare. It has even reached the point where I considered becoming an artist! *Shudders* Dark times... I have been attempting to implement a system for choosing which rooms should be spawned on a given cell. This would use the outputted “DoorStatus” map that I previously made. I figured this would have been fairly straightforward but boy was I wrong. There is a reason why complex programming should be done in C++."

references:
  - name: "@SketchyNeil on Twitter"
    link: "https://twitter.com/SketchyNeil"
  - name: "@SketchyNeil's development blog"
    link: "https://nbeattie768.wixsite.com/design/blog-1?fbclid=IwAR1BPBOBYgPrQSEHnk2481bP8NsUCiZ_ENboov90yQb_ivpyO94JPS1nKVM"
---

*I should preface this by thanking [@SketchyNeil](https://twitter.com/SketchyNeil) for helping me implement this part of the level generation. I've been staring at the same set of blueprints for over a week and I'm sure I would still be had he not come in and got me back on track.*

#### I knew procedural generation would be hard, but I didn't think it would have been THIS hard!

I've spent the past week working on this nightmare. It has even reached the point where [I considered becoming an artist!](https://twitter.com/ProfessorDudley/status/1095748183530049536) \**Shudders*\* Dark times...

I have been attempting to implement a system for choosing which rooms should be spawned on a given cell. This would use the outputted "DoorStatus" map that I previously made. I figured this would have been fairly straightforward but boy was I wrong. There is a reason why complex programming should be done in C++. Blueprints has this interesting ability to appear to be working sequentially, but in reality, it is processing a lot of things as quickly as it can. Let me explain in a different way:

I have a for each loop which iterates through each item in an array of fruits and Vegetables. Our array contains **[Apples, Oranges, Cucumbers, Potatoes, Bananas, Carrots, Strawberries, Apricots]**. In each iteration, we want to first print out what item in the array is being processed. Then we want to find out if it is a Fruit or a Vegetable. If it is a Vegetable we want to remove it from the array. This is a simplified version of what I was attempting to do. Substitute the fruit and veg for rooms and we are checking to see what doors each room has, removing rooms with **INVALID** doors.

What I discovered is that when doing this for each loop, unreal actually calls each action at the same time in order. It doesn't wait until the end of an iteration before sending the next one through. Somehow this means that while one item is being removed from the array, other invalid items can slip through. Honestly, I couldn't explain why. Surely it would still process the same just faster. For whatever reason it wasn't filtering out my rooms properly.

#### I was honestly considering changing my entire project because of this issue.

Thankfully, [@SketchyNeil](https://twitter.com/SketchyNeil) is an absolute legend. He has been helping me with this issue for the past few nights and we have finally got it functional. It's not pretty, but it works. And at this point, that is all I want from this.

<div class="embed">
<div class="iframe-container">
<iframe src="https://blueprintue.com/render/2oc3hmux" scrolling="no"></iframe>
</div>
<h5>His method used a crazy amount of branch nodes and boolean logic.</h5>
</div>

In the future I want to go back and refactor this. I don't fully understand how this system works, I just know it does. What I'd like to end with is a system where the spawning decisions can be weighted to avoid generation errors. As an example, I'd like to avoid having the dungeon loop around on itself, trapping it. For example, a condition that kept track of how many turns the dungeon had made. This would be done to prevent the dungeon from looping in on itself, trapping future rooms.

After refactoring, the code would be cleaner and should be better optimised. I would also understand the system better and hopefully would have a system for weighted outputs. This is the ideal system, but I will be focusing on getting the rest of the core mechanics functional first.
