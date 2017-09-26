---
layout: post
title: Text Message Abbrevation
date: 2017-09-26
---
{% highlight java %}
import java.util.Map;
import java.util.HashMap;
import java.util.Scanner;
 
public class TextMsgExpander {
    
    public static void main(String[] args) {
       
      Scanner scnr = new Scanner(System.in);
      System.out.println("Enter text: ");
      String userInput = scnr.nextLine();
      System.out.println("You entered: " + userInput);
       
      // Create new instance of Hash Map
       
      HashMap<String, String> map = new HashMap<String, String>();
       
      //Key value pairs
       
      map.put("LOL", "laugh out loud");
      map.put("IDK", "I don't know");
      map.put("BFF", "best friend forever");
      map.put("TTYL", "talk to you later");
      map.put("JK", "just kidding");
      map.put("TMI", "too much information");
      map.put("IMHO", "in my humble opinion");
       
      // Loop through user input string. Replace keys with values.
       
      for (Map.Entry<String, String> entry : map.entrySet()) {
         if (userInput.contains(entry.getKey())) {
            userInput = userInput.replaceAll(entry.getKey(), entry.getValue());
         }
      }
       
      System.out.println("Expanded: " + userInput);
 
      return;
 
 
   }
}
{% endhighlight %}
