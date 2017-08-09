---
layout: post
title: Alarm Clock
date: 2017-08-09
---
This is an alarm clock program I wrote for practice. It takes the user input, e.g. "August 10, 2017 0800", converts it to a datetime object, subtracts from it the current_time object, casts that to total_seconds, sleeps for that amount, then opens a youtube link. Run in terminal.
{% highlight python %}
from datetime import datetime
import time, webbrowser
 
current_time = datetime.today() 
user_dt = input("Enter a date and time: ")
converted_user_input = datetime.strptime(user_dt, '%B %d, %Y %H%M')
time_until_alarm = converted_user_input - current_time
total_seconds = time_until_alarm.total_seconds()
time.sleep(total_seconds)
webbrowser.open_new("https://youtu.be/LdWbPJOrW4c")
{% endhighlight %}


