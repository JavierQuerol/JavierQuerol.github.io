---
layout: post
title:  "A NSManagedObject category to retrieve the first letter from an attribute"
date:   2015-01-03 11:35:22
---

Sometimes you want to order your `NSManagedObjects` by name, but not all the objects has the first letter uppercased, and you don't want to create a new property just to store the first letter. In this case you can call a method that gives you the first letter on runtime.

{% gist 4a924088c3aa1c20411f %}

{% gist 4f456265b8a33f065a7e %}

This category allows you to create sections in your `UITableView` sorted by name like a Contact list.