---
layout: post
title: UILabel category to use html as text keeping the format
---

## Heading

Vivamus sagittis lacus vel augue rutrum faucibus dolor auctor. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.

### Code

Cum sociis natoque penatibus et magnis dis `code element` montes, nascetur ridiculus mus.

{% highlight objective-c %}
//
//  UILabel+HTML.m
//  TicketManager
//
//  Created by Javier Querol on 02/10/14.
//  Copyright (c) 2014 treeNovum. All rights reserved.
//

#import "UILabel+HTML.h"

@implementation UILabel (HTML)

- (void)jaq_setHTMLFromString:(NSString *)string {
	
	string = [string stringByAppendingString:[NSString stringWithFormat:@"<style>body{font-family: '%@'; font-size:%fpx;}</style>",
											  self.font.fontName,
											  self.font.pointSize]];
    self.attributedText = [[NSAttributedString alloc] initWithData:[string dataUsingEncoding:NSUnicodeStringEncoding]
                                                           options:@{NSDocumentTypeDocumentAttribute: NSHTMLTextDocumentType,
																	 NSCharacterEncodingDocumentAttribute: @(NSUTF8StringEncoding)}
												documentAttributes:nil
                                                             error:nil];
}


@end

{% endhighlight %}

Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa.
