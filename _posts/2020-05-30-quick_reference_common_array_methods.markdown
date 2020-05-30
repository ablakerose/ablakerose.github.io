---
layout: post
title:      "Quick Reference: Common Array Methods"
date:       2020-05-30 17:59:44 +0000
permalink:  quick_reference_common_array_methods
---


A quick reference for Array methods. 

ADD / DESTRUCTIVE

`.push()`
Action: Adds elements to the end of an array
Returns: Length of the updated array 

`.unshift()`
Action: Adds element(s) to the beginning of an array
Returns: Length of the updated array

ADD / NONDESTRUCTIVE

Spread Operator
Action: Allows us to spread out the contents of an existing  Array into a new Array, adding new elements but preserving the original: 
Returns: contents of newly created array 

REMOVE / DESTRUCTIVE: 

`.pop()`
Action: removes the last element in an array, destructively updating the original Array
Returns: the last element [the removed element] of the array

`.shift()`
Action: removes the first element in an Array, mutating the original
Returns: the first element [the removed element] of the array

REMOVE / NONDESTRUCTIVE 

`.slice()`
Action: supply two arguments; (1) the index where slice should begin and the index before it should end
Returns: 
* No argument provided: returns new array with the same elements as the original
* Both arguments provided: the element of the first index until the element before the second index provided
* First argument provided: the element of the first index provided through the end
* Providing negative index as the first argument, the engine counts from the last element of the array


