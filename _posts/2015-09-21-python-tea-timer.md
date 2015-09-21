---
layout:     post
categories: python tea timer
summary:    A quick Python script to stop me forgetting about my cup of tea.
---

I like to drink a lot of tea at work but I have developed a bad habit of going back to my desk and forgetting I have a cup of tea brewing in the kitchen. Then, a half hour or so later I remember and return to an over-stewed bitter cup of tea that I have to throw away.

In an attempt to fix this bad habit I wrote a quick Python script which will pop up a notification on my PC after 3 minutes to remind me to go get my tea:

{% highlight python %}
#!/usr/bin/python3
from gi.repository import Notify
import sys
import time

notify_title = 'Tea time!'
notify_body = 'Your tea is ready, go get it!'
notify_icon = 'dialog-information'

default_wait_time = 180

def usage():
    print("Usage: ",sys.argv[0],"<wait_duration_in_seconds>")

if len(sys.argv)>2:
    usage()
    sys.exit()
    
wait_time = default_wait_time
if len(sys.argv)>1:
    try:
        wait_time = int(sys.argv[1])
    except ValueError:
        usage()
        print("Duration must be integer")
        sys.exit()

time.sleep(wait_time)

Notify.init("Tea timer")
notification=Notify.Notification.new(notify_title, notify_body, notify_icon)
notification.show()
{% endhighlight %}

You can also specify the wait time duration as a command line argument if you want the tea to brew longer or shorter than 3 minutes. 

It should work on any Linux distribution but note that it uses Python 3. If you wish to use Python 2 you will need to change the format of the print statements.
