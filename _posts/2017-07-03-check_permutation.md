---
layout: post
title: "Check Permutation"
date: 2017-07-03
---
Given two strings, write a method to decide if one is a permutation of the other.
{% highlight python %}
def check_permutation(string1,string2):
    '''Determine if two strings are permutations of each other.'''
    if len(string1) != len(string2):
        return False
    sorted_string1 = sorted(string1)
    sorted_string2 = sorted(string2)
    if sorted_string1 == sorted_string2:
        return True
    else:
        return False
 
if __name__ == '__main__':
    print(check_permutation('bate','tabe'))
    print(check_permutation('hello','bellow'))
    print(check_permutation('nyct','tycn'))
{% endhighlight %}
