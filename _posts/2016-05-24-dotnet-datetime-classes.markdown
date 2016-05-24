---
layout: post
title:  ".NET date and time structures"
date:   2016-05-24 22:00:00 +0800
categories: blog
---
I'm currently working on a very simple web API which serves data to a mobile app. One of the properties of the data is a time field. Until this instance I've never had to work on a problem where the time has to be displayed based on where the user is seeing the time from. Simply said if a server located at EAST-EUROPE returns the time as "10:30", a user viewing that time from Singapore should see it as "18:30". While solving this problem I learnt a lot about how to store time and I've tried to summarize that below.

First of all .NET offers the 2 date time structures.

- [DateTime](https://msdn.microsoft.com/en-us/library/system.datetime(v=vs.110).aspx)
- [DateTimeOffset](https://msdn.microsoft.com/en-us/library/system.datetimeoffset(v=vs.110).aspx)

### When should I use DateTime?

> Use DateTime when you implicity know what time zone the data is coming from. 

For example at my work all transactions that we receive are timestamped and this time will always be UTC-4. Hence we do no need to know what is the offset of the time and hence use DateTime. For reasons like saving space in database etc.

### When should I use DateTimeOffset?

> DateTimeOffset should be used if you are referring to a specifc instant in time.

I must say it took a while for me to understand the what DateTimeOffset meant. The above statement best describes when you need to use it. A simple example is time of your birth. Lets say you were born exactly when I wrote this post(unlikely that you'll be reading this anytime soon but neverthless). Then if you want to record that time you need to use DateTimeOffset which will give you a value of "5/18/2016 3:47:59 PM +08:00". 

This means you were born on the 18th of May 2016 at 3:47 PM UTC+8. This is an absolute value relative to UTC which tells you exactly at what instant you were born at. If you had chosen to use DateTime you'd only get "5/18/2016 3:47:59 PM" from which you can't really say the exact time.

I realised that this topic has been heavily blogged about like [here](https://msdn.microsoft.com/en-us/library/bb384267(v=vs.110).aspx), [here](https://blogs.msdn.microsoft.com/davidrickard/2012/04/06/datetime-and-datetimeoffset-in-net-good-practices-and-common-pitfalls/) and [here](https://mgrowan.wordpress.com/2014/06/03/no-need-to-use-datetime-utc-again/). It is confusing when there are multiple ways to do the same thing.

I just looked up at how Ruby does it and unsurprisingly they have only [one class](http://www.tutorialspoint.com/ruby/ruby_date_time.htm) for retrieving system time. Rails has [an API](http://api.rubyonrails.org/classes/ActiveSupport/TimeWithZone.html) for working with times from different zones which I feel is used only in special scenarios.