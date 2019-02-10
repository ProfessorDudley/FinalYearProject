---
layout: post
title: "Unreal Engine and Git-LFS 2.0?"
subtitle: "Git's bigger brother: Git-LFS 2.0"
tags: [Unreal Engine, Git, GitHub]
date: 2019-02-05

excerpt: "I was trying to find out how git can be used with unreal engine. Git encourages parallel development using a branch based version control system. What this means is everyone who is collaborating on a project have their own local copies of the project, including all the branches. It isn't possible to lock files for editing like in Perforce or Subversion."
references:
  - name: "Parallel Development"
    link: "https://nvie.com/posts/a-successful-git-branching-model/"
  - name: "SRombauts"
    link: "https://github.com/SRombauts/UE4GitPlugin"
---

#### So I was doing some reading up on GitHub...

I was trying to find out how git can be used with unreal engine. Git encourages [parallel development](https://nvie.com/posts/a-successful-git-branching-model/) using a branch based version control system. What this means is everyone who is collaborating on a project have their own local copies of the project, including all the branches. It isn't possible to lock files for editing like in Perforce or Subversion.

This limitation makes working with git in Unreal Engine and Blueprints really difficult. .uasset files can't be easily merged when you try to merge branches in git. You would have to choose which file to keep and which to delete. So if I edit the player character and made them jump, but at the same time someone else made them swim, one of us would have to **loose our work**.

#### So Git is useless then for Blueprint game development then?

On it's own, Yes. But Git-LFS is a solution.

[Git-LFS](https://github.blog/2017-03-02-git-lfs-2-0-0-released/) (Git Large File Storage) is like Git's bigger brother. It replaces large files (such as audio files and textures) in your repository with pointers. The large files can then be stored on a shared remote server. Pretty cool. What is even cooler though is that as of version 2.0 files can be locked for editing using this system, and it doesn't effect the normal Git workflow.

#### So Git-LFS 2.0 supports the same checkout system as Perforce and Subversion, but what's the catch?

The catch is that Unreal Engine doesn't support Git-LFS 2.0, or even fully support Git for that matter. Is there a way to work around this? In theory, yes. [SRombauts](https://github.com/SRombauts/UE4GitPlugin) has kindly made a plugin for Unreal that adds Git-LFS 2.0 support into Unreal Engine, replacing the built in Git version control tool. Even without this plugin, it may still be possible, but it would require having a Git client such as GitHub Desktop open at the same time to manage checking out files and committing changes.

None of this is useful information to have for my current project however since I don't need to worry about collaboration. But it is still interesting to find out how I can use Git for version control in future projects.
