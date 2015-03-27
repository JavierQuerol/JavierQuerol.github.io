---
layout: post
title:  "Map and Filter a NSArray in Objective-C"
date:   2015-01-11 11:28:22
---

Inspired in the Swift map and filter, I decided to port that feature into Objective-C and I realize that is very useful and I'm using it quite often.

{% gist 19ba0a998cfa000994cd %}
{% gist 08304cbbb923d4f24146 %}

Example:
{% highlight objective-c %}
NSArray *test = @[@2,@3,@4,@5,@6,@7,@8,@9,@10];
	
NSArray *filtered = [test jaq_filter:^BOOL(id item) {
	NSNumber *number = item;
	return (number.integerValue % 2 == 0);
}];

NSArray *mapped = [test jaq_map:^id(id item) {
	NSNumber *number = item;
	return @(number.integerValue*2);
}];
{% endhighlight %}

The same approach can be used in `NSSet` with ease.