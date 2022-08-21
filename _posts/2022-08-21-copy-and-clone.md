---
title: The difference between copy and clone in Python
category: "Coding"
tags: [Python, Data Analysis]
---

# What's the difference between copy and clone in Python?
If you copied something, you just created a new path to render an item.
If you cloned something, you created a totally new item.

For example, you have a list A, which is [1,2,3,4], then you copied A to creat a new list B, and cloned A to create a new list C.
C is a totally separated list, but A and B actually render the same list, with just 2 names.

So if you changed B to [1,2,2,4], and display A, you would find A being changed to [1,2,2,4].
But when you changed C to [1,2,2,2], nothing would happen on A.