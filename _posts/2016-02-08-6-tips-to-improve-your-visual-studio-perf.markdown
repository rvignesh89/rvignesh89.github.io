---
layout: post
title:  "6 tips to improve your Visual Studio Perf!"
date:   2016-02-08 13:49:42 +0800
categories: blog
---
We all know that by default Windows comes with a lot fancy animations and effects which apart from annoying us, also reduces the performance of your computer. If you are reading this and have not yet turned off the default Windows animations please stop. Follow this [link](http://www.howtogeek.com/128306/how-to-disable-the-animations-on-the-windows-8-start-screen/) to do that first before coming back here!

**Warning:** I'm a web developer so some of things I've mentioned below might not apply to you. Also, I use [Resharper](https://www.jetbrains.com/resharper/) a LOT to help me be faster with my development. Because of which I can turn off some features in Visual Studio as mentioned below.

#### 1. Startup

The biggest turn off when using anything happens when you open the application and it takes 5s to start. If you agree with me you can go to *Options->Environment->Startup* and select *Show Empty Environment* when starting up. If you do that then I'm guessing you also don't need the Microsoft news content to be updated so you can uncheck "Download content every" option.

![disable startup](/images/startup.png "Disable Startup Image")

#### 2. Tracking Active Item

This is something once turned off brings a noticeable difference in the experience. Although this is quite a convenient feature to have especially in large projects, you won't have to know where this file all the time. In Resharper whenever you are editing a file and you want to locate the file in the solution explorer you use the *Shift+Alt+L* shortcut. I quite frequently use this along with the *Cntl+Shift+F10* to open the context menu for the file.

![disable active item](/images/active_item.png "Disable Active Item Tracking")

#### 3. Navigation Bar

![nav bar](/images/nav_bar.png "Visual Studio Navigation Bar")

Okay this one is something I'm not sure if it really improves the performance. But the reason I removed the navigation bar is to increase the amount of code I see, which does indirectly improve my performance :D But then again sometimes you want to look at the methods the class has. For this, I use the Resharper shortcuts *Alt+\\* to list the methods in the class which is way way more faster than moving your move to the Navigation Bar, listing and clicking. Simply said I consider using the mouse a sin!

Here is how to turn it off.

![nav bar stop](/images/nav_bar_stop.png "Disable Navigation Bar")

#### 4. Status Bar

![status bar](/images/status.png "Status Bar")

This bar lists down information about your line number, current build status, error and warnings numbers etc. In my case I don't want to know these numbers all the time. For line numbers, I display it in my text editor itself. I also configured Visual Studio to automatically display *Output->Build* tab when I build the project so the error and warning counts will be displayed there. Also considering I can see I extra line of code I chose to disable this bar as well, as shown below.

![disable status bar](/images/hide_status_bar.png "Hide Status Bar")

#### 5. Margin Indicator

Margin Indicators are mostly used for visual cues of your code. You can look [here](https://msdn.microsoft.com/en-us/library/aa238792.aspx) to know more about them. I mainly use this bar for inserting debug points for which I use the shortcut *F9* to add and remove. You can turn this off as shown here,

![disable indicator margin](/images/indicator_margin.png "Disable Indicator Margin")

#### 6. Turn off all toolbars

Okay, the only reason I did this is to force myself to find and use shortcuts for commands that I wanted to use. The only toolbar that I found useful is the Source Control. But considering my ultimate goal which was to use Visual Studio without a mouse, I chose to sacrifice that toolbar. Also we might be moving to Git as our internal SCM soon. Hence this might be only a temporary state.

That's it! Hope these tips help you to become a craftsmen at work!

If you want to speed up ReSharper you follow some of the tips from [here](https://confluence.jetbrains.com/pages/viewpage.action?pageId=37228482).
