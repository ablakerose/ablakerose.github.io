---
layout: post
title:      "Enter your title here"
date:       2020-05-17 11:12:03 +0000
permalink:  enter_your_title_here
---


As I explained in this post, I built the Holistic Wealth App as a way to visualize and apply Manfred Max Neef’s Human Scale Development methodology to my everyday life— identifying in real time what needs my activities are satisfying and how I can choose synergic satisfiers more often to increase the amount of frequency of satisfying needs. I’ll discuss below the design of the application through three principles of human scale development.


*1. Human needs must be understood as a system: that is, all human needs are inter-related and interactive. *

The relationship between Needs and Satisfiers in this application is perhaps the most critical component to get right to effective bringing Neef’s concept to life. different satisfiers to life. The nine needs are constant, but satisfiers can be violators/destroyers (satisfy one need but detract from others), pseudo-satisfiers (false sense of satisfaction), and synergic satisfiers (satisfy multiple needs at once). 

Currently, the functionality captures synergic satisfiers. The following checkbox function allows a user to select from a menu of needs. The user is given the option to check off needs associated to an activity (satisfier). The checkbox next to each need goes through the following logic. When the box is checked, if the index of that need found exists in the needs associated with that satisfier (i.e. indexOf returns a value greater than (-1)), the function locates that index value and removes it (‘1’) from the array. If the value does not exist in the need_ids array, the value is pushed into the array, taking its place with that satisfiers existing needs. 

```
handleCheckedBox = e => {
     const value = e.target.value;
     const need_ids = [...this.state.need_ids];
     const index = need_ids.indexOf(value);
     if (index > -1) {
         need_ids.splice(index, 1);
     } else {
         need_ids.push(value);
    }
     this.setState({
          need_ids
     });
};
```

The next step in enhancing this apps functionality is to determine how to more accurately reflect the impact of violators and pseudo-satisfiers.

*2. Fundamental human needs must be understood as a system, the dynamics of which does not obey hierarchical linearities. *

Another key principle is that each of the needs (with the exception of subsistence) is considered to be as important as any other. Currently, the app functionality captures this principle by applying the same calculation for each Need level total. 

```
const NeedWorth = props => {
     const levelTotalPercentage = () => {
          const total = props.need.satisfiers.reduce(
               (sum, satisfier) => sum + satisfier.value,
               0
          );
          return total * 10;
};
```

The next step here could be to include a minimum for satisfying subsistence to demonstrate its difference over the other needs. 

*3. Development is about people and not about objects.*

This principle is the core of both Human Scale Development (HSD) and embedded into the construction of the application. Neef asks, “how can we determine whether one development process is better than another?” Economic theory uses gross national product (GNP) as an indicator for the qualitative growth of objects, so Neef contemplates how in HSD to find an indicator for the qualitative growth of people. He answers the question saying, the process that allows the greatest improvement in people’s quality of life and asserts qualify of life is determined by people’s opportunities to satisfy their fundamental human needs. 

Thus future functionality in this respect will be geared toward ways to identify synergic satisfiers (perhaps through an interface of clickable activities), to identify what activities are giving them more value and perhaps how other small changes in other respects can afford more value.  

