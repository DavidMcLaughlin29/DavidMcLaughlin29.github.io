---
layout: post
title: Paint Estimator
date: 2017-09-24
---
Calculates the gallons and can(s) of paint needed for area of a wall.
{% highlight java %}
import java.util.Scanner;
import java.lang.Math;

public class PaintEstimator {
    
    public static void main(String[] args) {
      
       Scanner scnr = new Scanner(System.in);
       double wallHeight = 0.0;
       double wallWidth = 0.0;
       double wallArea = 0.0;
       double gallonsPaintNeeded = 0.0;
       double cansNeeded = 0;
      
       final double squareFeetPerGallons = 350.0;
       final double gallonsPerCan = 1.0;
      
       System.out.println("Enter wall height (feet): ");
       wallHeight = scnr.nextDouble();
      
      // Prompt user to input wall's width
       System.out.println("Enter wall width (feet): ");
       wallWidth = scnr.nextDouble();
      
      // Calculate and output wall area
       wallArea = wallHeight * wallWidth;
       System.out.println("Wall area: " + wallArea + " square feet");
      
      // Calculate and output the amount of paint in gallons needed to paint the wall
       gallonsPaintNeeded = wallArea/squareFeetPerGallons;
       System.out.println("Paint needed: " + gallonsPaintNeeded + " gallons");
      
      // Calculate and output the number of 1 gallon cans needed to paint the wall, rounded up to nearest integer
       cansNeeded = Math.round(gallonsPaintNeeded / gallonsPerCan);
       int cansNeededInt = (int)cansNeeded;
       System.out.println("Cans needed: " + cansNeededInt + " can(s)");  

       return;
    }
    
}
{% endhighlight %}
