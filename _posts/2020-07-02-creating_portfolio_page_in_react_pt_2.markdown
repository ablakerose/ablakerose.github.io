---
layout: post
title:      "Creating Portfolio Page in React (Pt. 2)"
date:       2020-07-02 21:37:09 +0000
permalink:  creating_portfolio_page_in_react_pt_2
---


Today I’m discussing my process for continuing to build out my portfolio page, adding CSS styling.  

## Using Grid System from React-MDL

I added inline styling to the landing page as indicated below. For react MDL, there is a unit grid system, offering twelve units across. Understanding the Grid System for React-MDL makes easy work of styling the website pages. First, I imported the Grid and Cell components into the page using import { Grid, Cell } from "react-mdl” as seen below and styled the page to have 12 units across. 

```
import React, { Component } from "react";
import { Grid, Cell } from "react-mdl";


class LandingPage extends Component {
    render() {
        return (
            <div style={{ width: "100%", margin: "auto" }}>
                <Grid className="landing-grid">
                    <Cell col={12}>
                        {/* <img
                            src="https://unsplash.com/photos/tO9r7s7tqhE"
                            alt="avatar"
                            className="door-img"
                        /> */}
                    </Cell>
                </Grid>
            </div>
        );
    }
}

export default LandingPage
```


## Inside app.css

Inside the App.css file, I defined a class to correspond with the Grid classname on the landing page and pasted the relevant CSS styling from the gradient-UI website chosen. I followed the same process to add color to the header (1) gave header inside the App.js file a className, put that class in App.css and pasted relevant CSS information.   
 
 
## Including a Block with Styled Text & Clickable Icons

In order to create a block with text inside, I created a <div> with an <h1> inside and styled each of them in the App.css.  I put in a line break with an <hr> and included a list of languages and frameworks I’m familiar with. Finally, I included several social media icons that will become clickable to relevant websites. 

The icons came from Font Awesome BootstrapCDN. I included the CSS link in the index.html within the head tag below the others. I have each of the icons inside a separate <a> tag, all within a <div>.  

```
import React, { Component } from "react";
import { Grid, Cell } from "react-mdl";


class LandingPage extends Component {
    render() {
        return (
            <div style={{ width: "100%", margin: "auto" }}>
                <Grid className="landing-grid">
                    <Cell col={12}>
                    
                    <div className="banner-text">
                        <h1>Full Stack Web Developer</h1>
                        <hr />
                        <p>
                            HTML/CSS | JavaScript | React | React Native | Ruby | Ruby on Rails
                        </p>
                    <div className="social-links">
                       [...]
                    </Cell>
                </Grid>
            </div>
        );
        }
    }


export default LandingPage;
```


 Next time, I plan to make the links all navigate properly. 
