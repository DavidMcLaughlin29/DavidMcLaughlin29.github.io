---
layout: post
title: Song Shuffler
date: 2017-09-11
---
This takes songs that the user inputs, shuffles them, and outputs them to a text file.
{% highlight python %}
from random import shuffle
 
songs = input("Enter your songs, separated by a comma and a space: ")
 
# convert input to a list of strings
converted_songs = songs.split(', ')
 
# shuffle list of songs
shuffle(converted_songs)
 
# creates file song.txt
with open ('songs.txt','w') as f:
     
    for index, song in enumerate(converted_songs, start=1):
        string_of_songs = ("{} {} \n").format(index, song)
        f.write(string_of_songs)
{% endhighlight %}

