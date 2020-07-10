---
layout: post
title:      "Creating Portfolio Page in React (pt. 3)"
date:       2020-07-10 21:46:39 +0000
permalink:  creating_portfolio_page_in_react_pt_3
---

I’ve been using React-MDL to set up my portfolio site. As explained on their website, React-MDL is a set of React Components for Material Design Lite (MDL) which is a library of vanilla components maintained by Google. In the post, I will go into some of the code that went into the projects page. 

```
import React, { Component } from "react";
import { Tabs, Tab } from "react-mdl";
import "../App.css";

class Projects extends Component {

    constructor(props) {
        super(props);
        this.state = { activeTab: 0 }
}

toggleCategories() {
    if (this.state.activeTab === 0) {
        return (
            <div>
                <h1>This is React</h1>
            </div>
        );   
    } else if (this.state.activeTab === 1) {
        return (
            <div>
                <h1>This is Ruby on Rails</h1>
            </div>
        );
    }
}

    render() {
        return (
            <div className="category-tabs">
                <Tabs
                    activeTab={this.state.activeTab}
                    onChange={(tabId) => this.setState({ activeTab: tabId })}
                    ripple
                >
                <Tab>React</Tab>
                <Tab>Ruby on Rails</Tab>
                <Tab>JavaScript</Tab>
                </Tabs>
                <h1>Projects</h1>
            </div>
        );
    }
}

export default Projects;
```

I’ve been using React-MDL to set up my portfolio site. As explained on their website, React-MDL is a set of React Components for Material Design Lite (MDL) which is a library of vanilla components maintained by Google. In the post, I will go into some of the code that went into the projects page. 

## Tabs and Tab components
    
After importing the Tabs and Tab components from react-mdl into the project page component, they are ready to be used. I’m setting the state of the Tabs components equal to whatever the prop activeTab is equal to at any given time and using on onChange event to set it.  

## toggleCategories

The function that controls what item is seen is placed above and uses an if else statement to render the correct tab. Each of the `<Tab>` elements has an index beginning at 0. Therefore, in order for the user to be able to access the proper tabs, all that needs to be done is for the if else statement in the function to return the appropriate div associated with the activeTab. 

