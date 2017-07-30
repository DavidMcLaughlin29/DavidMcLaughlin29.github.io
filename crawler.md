---
layout: page
title: Crawler
permalink: /Crawler/
---
Utilizes the requests library to grab all the links on a page and return them in a list. I did this for practice. It could be modified in all sorts of ways to grab whatever you wanted from a web-page.
{% highlight python %}
import requests

def grab_page(url):
    '''Function that grabs a web-page and its content.'''
    page = requests.get(url)
    content = page.text
    return content
 
def grab_next_link(page):
    '''Function to find next link'''
    start_link = page.find('<a href=')
    if start_link == -1:
        return None, 0        
    start_quote = page.find('"', start_link)
    end_quote = page.find('"', start_quote + 1)
    url = page[start_quote + 1:end_quote]
    return url, end_quote
 
def grab_all_links(page):
    '''Gets all the links from a page and returns them in a list.'''
    links = []
    while True:
        url, endpos = grab_next_link(page)
        if url:
            links.append(url)
            page = page[endpos:]
        else:
            break
    return links
 
links = grab_all_links(grab_page("https://xkcd.com/"))
 
print(links)
{% endhighlight %}