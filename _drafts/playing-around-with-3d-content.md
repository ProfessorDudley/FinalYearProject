---
layout: default
title: "Playing Around with 3D content"
subtitle: "This page is best viewed with Safari on iOS"
tags: [Apple ARKit, Web Development, 3D Modelling, Asset Packs]
date: 2019-02-16
references:
    - name: "Unreal Marketplace"
      link: "https://www.unrealengine.com/marketplace"
    - name: "Synty Store"
      link: "https://syntystore.com"
    - name: "The Polygon Dungeon Pack"
      link: "https://www.unrealengine.com/marketplace/polygon-dungeon-pack"
    - name: "Marmoset Viewer"
      link: "https://marmoset.co/viewer/"
    - name: "Apple ARKit and Quicklook"
      link: "https://developer.apple.com/arkit/"
    - name: "USD file format"
      link: "https://graphics.pixar.com/usd/overview.html"
---

#### This time, web development wasn't a random endevour

I recently recieved an email from Teesside University stating that I had until the 18th of March to upload images of my project to their intranet. This is in preparation for their **ExpoTees** event in May. The 18th of March isn't that far away and I still only really have print strings to show for my project. So I had to make some schedule changes. Now I am making a mock level that is hand built. I can use this to get the project images needed for the event without needing to get much further in development so soon. What I have done so far is blocked out a room. Put some orange boxes here, a gray floor there, drop the hero in the room and splatter some enemies around...

<div class="embed">
<div class="iframe-container">
<img src="" alt="">
</div>
<h5>Hm. Looks a bit rubbish don't it?</h5>
</div>

What this meant was I needed art assets. Before starting the project, I had already decided on which asset pack I was going to use. The available free asset packs didn't fit the aesthetic vision that I had, so I had to look at paid options. [The Unreal Marketplace](https://www.unrealengine.com/marketplace) has a large collection of asset packs provided by developers for use in Unreal Engine projects. I found an asset pack by Synty Studios [Synty Studios](https://syntystore.com") - [The Polygon Dungeon Pack](https://www.unrealengine.com/marketplace/polygon-dungeon-pack) which was close enough to my desired aesthetic.

<div class="embed">
<div class="iframe-container">
<img src="" alt="">
</div>
<h5>Ohh, looks cool doesn't it? Wouldn't it be cool if it actually existed? <span style="font-style: normal;">🤔</span></h5>
</div>

#### Well of course I was going to find a way to best present 3D models wasn't I?

[Marmoset Viewer](https://marmoset.co/viewer/) was my first idea but that seemed to get complicated and I didn't actually want to spend much more time on this website (it's odd hearing myself say that). So what else could I use instead of Marmoset Viewer? Images would work, but that is sooo 2018. We live in the future. We have smartphones that have built in augmented reality capabilitys for goodness sakes. 

##### Hey, that's actually a pretty cool idea.

In 2018 Apple released iOS 12 and with it, [ARKit](https://developer.apple.com/arkit/) - their Augmented Reality code library for iOS devices. And they also announced a new file format: USDZ. An extention of a preexisting file format: [USD created by Pixar Animation](https://graphics.pixar.com/usd/overview.html). I'll avoid going into much of the technical details but essentially a USD file is just like any other 3D file format like *.fbx* and *.obj*. A USDZ file is more like an archive file; it contains the 3D model, and any texture files that are used on the model (Albedo, Normal, Metallic and Roughness, etc...). It is all neatly packed into one portable file (which is somehow smaller than either an *.fbx* or *.obj*).

Now the intresting bit about this file format is that it can be easily embeded in a website. Literally just add the file as a link and the browser will open it in a 3D viewer, completly textured and scaled. And it can also be viewed in the real world using ARKit on iOS devices. And that is the only problem with this solution. It only works on Safari running on iOS devices. Android phones and desktop computers will only see an image of the model. The Marmoset Viewer is available on all devices on the majority of browsers. 

But given I'm not a 3D modeller, there won't be very many instances where I'll need to show off a 3D model. So for the extra time it would take, it would be better for me to spend that time actually working on the project.

#### But I'm still going to include some examples of the assets I'm going to be using.

<a rel="ar" href="/models/male_hero.usdz">
<img src="/images/models/male_hero.jpg" alt="">
</a>
<h5>Sir Knight the First</h5>