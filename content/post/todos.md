---
Title: To-do
Date: 2012-07-24
---

To try developing a file-based service as described in the previous post, I've considered several applications that could make use of storing information in text files. These should be application where reliability and accessibility of information is important.

One of my first ideas was to implement a task/issue tracker. Issue tracking systems used by programmers are commonly installed on top of VCS  (git, mercurial, etc), but function as ordinary websites, storing tickets and discussions in a relational databases. Examples are TRAC, Mantis, RedMine, etc.

The idea was to make stored information more reliable by using file system instead of relational databases. The problem is that an issue tracker is a fairly complex application, it's implementation can take a lot of time and it does not fit good enough for a proof-of-concept application.

Recently, I have started looking at the ways people use textual data for personal task tracking. The simpliest application I've discovered was [todo.txt](http://todotxt.com/) - it is a set of simple services to help you edit your todo.txt file online. It is basically what I've been thinking about: you sync it with your dropbox and you have all your information in text files. Their website says:

> Countless productivity apps and sites store your tasks in their own proprietary database and file format. But you can work with your todo.txt file in every text editor ever made, regardless of operating system or vendor.

So yeah, basically, that's my idea.

The second thing I've found is far more interesting. It's called Emacs Org Mode and it's an editing mode for Emacs build for organizing tasks and making notes. The main idea is that making notes and creating tasks should be done together. Istead of having a special place for random notes and a separate place for tasks, you'd rather highlight something in your notebook and mark it as a task. A list of talks can be found [here](http://orgmode.org/talks.html).

Right now the idea of using Emacs as my quicknote application seems scary to me. I've already found some Sublime Text plug-in that works the same way, will be looking into it.

I've also found that RStudio (and IDE for R programming language, probably the one I will be using extensively at ETHZ) is good for making notes. It supports LaTeX syntax (which org-mode also does) and MarkDown syntax (which org-mode doesn't). I'll be looking into this stuff for a while before I can decide what setup is the best.
