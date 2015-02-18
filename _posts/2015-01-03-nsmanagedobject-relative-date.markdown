---
layout: post
title:  "Sorting NSManagedObjects by relative date"
date:   2015-01-03 11:35:22
---

Sometimes you want to order your `NSManagedObjects` by date, in this case I would like to group objects by relative date like Today, Yesterday, etc…

I'm using [`DateTools`](https://github.com/MatthewYork/DateTools) in order to make easy some relative dates, for the long time distance dates I'm using the default `doesRelativeDateFormatting` from `NSDateFormatter`.

{% gist 4a924088c3aa1c20411f %}

{% gist 4f456265b8a33f065a7e %}

This category allows you to create sections in your `UITableView` sorted by relative date by just setting the `sectionNameKeyPath` in your `NSFetchedResultsController` to the property available on the previous category:

{% highlight Objective-C %}
[[NSFetchedResultsController alloc] initWithFetchRequest:fetchRequest
 managedObjectContext:self.coreDataManager.managedObjectContext
 sectionNameKeyPath:@"relativeDate"
 cacheName:nil];
{% endhighlight %}