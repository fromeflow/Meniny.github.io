---    
layout: post    
category: "iOS"    
title:  "iOS UITableView: Appearance of HeaderView & FooterView for Section"    
tags: [iOS,UITableView]    
summary: "iOS UITableView: Appearance of HeaderView & FooterView for Section"    
---    
如果你想自定义header颜色，可以这样做:

{% highlight objective-c %}
[[UITableViewHeaderFooterView appearance] setTintColor:[UIColor redColor]]; 
{% endhighlight %}
	
如果你不想建立自定义视图，也可以这样(iOS6):

{% highlight objective-c %}
-(void) tableView:(UITableView *)tableView willDisplayHeaderView:(UIView *)view forSection:(NSInteger)section {
    if ([view isKindOfClass: [UITableViewHeaderFooterView class]]) {
        UITableViewHeaderFooterView* castView = (UITableViewHeaderFooterView*) view;
        UIView* content = castView.contentView;
        UIColor* color = [UIColor colorWithWhite:0.85 alpha:1.]; // substitute your color here
        content.backgroundColor = color;
    }
}
{% endhighlight %}
	
(通过UITableViewHeaderFooterView设置背景色的方法已经被废弃了。请用contentView.backgroundColor代替。)

在iOS 6以上，你可以通过以下方法改变背景色和文本色:

{% highlight objective-c %}
- (void)tableView:(UITableView *)tableView 
        willDisplayHeaderView:(UIView *)view 
        forSection:(NSInteger)section;
{% endhighlight %}
        
例如:

{% highlight objective-c %}
- (void)tableView:(UITableView *)tableView willDisplayHeaderView:(UIView *)view forSection:(NSInteger)section
{
    // Background color
    view.tintColor = [UIColor blackColor];

    // Text Color
    UITableViewHeaderFooterView *header = (UITableViewHeaderFooterView *)view;
    [header.textLabel setTextColor:[UIColor whiteColor]];

    // Another way to Setter the background color
    // Note: does not preserve gradient effect of original header
    // header.contentView.backgroundColor = [UIColor blackColor];
}
{% endhighlight %}
  
***    
<center>Powered by Meniny</center>    
<center>Contact <Meniny@qq.com></center>    
    
  
  


