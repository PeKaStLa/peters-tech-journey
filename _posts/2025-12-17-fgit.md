---
title: "fgit"
date: 2025-12-17
layout: post
---

When updating a git-repo you normaly have to run three commands: 

1. git add . 
2. git commit -m 'XXX' 
3. git push 

Instead you can add a command to .bashrc to execute all three commands in just one. (Important: $* saves the quotes but prevents adding more parameters to the git function. You can use $1 instead.)

function fgit() 
{ 
git add . 
git commit -a -m '$*' 
git push 
}
