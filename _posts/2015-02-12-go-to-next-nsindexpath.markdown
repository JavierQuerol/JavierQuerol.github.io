---
layout: post
title:  "Looping through NSIndexPath"
date:   2015-02-12 11:18:22
---
I'm currently making a form app, and I would like to access the next row on a `UITableView`, I don't want to care about if it's on the current section or not, so I created a `UITableView` category to retrieve the next `NSIndexPath`:

{% gist 94dae5a7108268c39d2d %}

{% gist f003cbaa6433184588fc %}

In case there are no next `NSIndexPath` it will return the very first position (loop).
