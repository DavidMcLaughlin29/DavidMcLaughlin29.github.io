---
layout: post
title: "Check Permutation"
date: 2017-07-03
---
{% highlight python %}
def check_permutation(string1,string2)
    '''Determine if two strings are permutations of each other.'''
    if len(string1) != len(string2):
        return False
    sorted_string1 = sorted(string1)
    sorted_string2 = sorted(string2)
    if sorted_string1 == sorted_string2:
        return True
    else:
        return False    
{% endhighlight %}