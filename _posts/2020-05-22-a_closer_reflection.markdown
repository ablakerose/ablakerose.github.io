---
layout: post
title:      "A closer look at satisfiers. "
date:       2020-05-22 11:26:36 -0400
permalink:  a_closer_reflection
---


This week I decided to improve the [Holistic Wealth app](https://ablakerose.github.io/what_do_wealth_and_poverty_really_mean) by simultaneously making it more functional for the user and tie its functionality closer to the economic theory it’s based on. 

I have achieved this by convert the previous “value” field to represent time spent doing each activity. The Human Scale Development theory is based on the fact that the individual is allowed to define what “qualities," “things," “activities" and “settings” satisfied a given need. Therefore, the original intent behind including a value field was to allow the user to subjectively input how readily that need was satisfied with any one activity. However, this representation was limited. 

As a user, I need to see the time allocated to my activities is being allocated to synergic satisfiers. In order to allow the user to see which activities fell into which type of satisfier (Synergic / Pseudo / Violator ), I decided to use time as the measure of the value of the activity with respect to how many needs each activity would satisfy. The value attribute replaced by time (in increments of 15 minutes) offers a truer “value” of each activity. 

With this methodology in place, I can then go about using the information imbedded in each satisfier to appropriately categorize them as Synergic / Pseudo / Violator.  Each activity will begin as neutral and with activity associated with needs, can change to become Synergic if it satisfies a certain number of needs relative to any it might violate. A violator can be categorized once there is code added to have a second section of checkboxes for detracting. The functionality of a category for Pseudo is different, because its categorization depends on beyond satisfying or detracting from a need. This depends on intending to satisfy a need but not achieving that goal. This is a forthcoming feature. 
