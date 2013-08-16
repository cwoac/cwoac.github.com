---
title: Announcing NVim
subtitle: Notational velocity in vim
layout: news
---

[Nvim][] is an clone of some of the main features of [Notational Velocity][nv] as a vim script.

NV/NValt remain one of the best arguments in favour of using OSX. A fast, efficient note-taking system that can be controlled entirely though the keyboard. 
Its combined search / title bar means you can just tell it what you want and you get the information you need or the ability to create a new note from the same command.
Unfortunately the codebase is too heavily dependant on OSX to make a port viable. 

A cross-platform clone of it already exists in the form of [nvpy][], however for various reasons[^1] it's not really for me.

Nvim is implemented as a vim script that is compatible with both vim and gvim, so it can be used in both as a gui app and in a terminal and on any platform that runs the requirements[^2]

Currently the codebase is a few defects short of the release version, however it is fully usable as is.


[nv]: http://notational.net
[nvpy]: https://github.com/cpbotha/nvpy
[nvim]: https://github.com/cwoac/nvim

[^1]: Ironically lack of cross-platform compatibility with nv's text format was one of them.
[^2]: vim, python2, xapian
