---
layout: post
title:      "Frequency Counters: The Antidote to a Messy Garage"
date:       2020-06-12 15:35:31 -0400
permalink:  frequency_counters_the_antidote_to_a_messy_garage
---


I’m standing inside a messy garage. I have a list of things I need to build my treehouse. I need to know what is contained in the piles of boxes before me so I can compare what I have to what I need. 

Without a frequency counter. I would look at the first item on my list, search the garage to see if I have it, note that down. I would go to the second item on my list, see if I have it, note that down. Repeat. The more items on my garage and the more items on my list, the longer this process would take. 

With a frequency counter. I would do a thorough passthrough of the garage one time to note all the items in the garage. I would emerge with an inventory that contains the name of each item, how many I have, and any other pertinent information. It does not matter how many items I have in the garage now, I have everything I need to know about them available at my fingertips. 

Rooting through the boxes multiple times wastes time. In this scenario, rooting through boxes equates to using nested loops, which would result in quadratic time O(n2).  Going through the boxes once and creating an inventory of the relevant information and using the inventory to return requested information is cleaner and saves time. In this scenario, the inventory is an object created and accessing that information can be done with O(n), linear time.  

The frequency counter algorithm is a way of breaking down the contents of an array or a string, storing those in an object, and then more easily comparing that breakdown to another object. 
