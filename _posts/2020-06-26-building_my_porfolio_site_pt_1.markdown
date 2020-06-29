---
layout: post
title:      "Building My Porfolio Site (pt 1)"
date:       2020-06-26 16:25:04 -0400
permalink:  building_my_porfolio_site_pt_1
---


I’m building my portfolio page with React with React-MDL for styling and documenting it here. 

I used create-react-app portfolio-bloke
cd portfolio-blake
npm start

**### Delete Boiler Plate**

One the app is running, delete all the boiler plate code files to make room for new code. This includes deleting files public: favicon.ico, manifest.json; src: logo.svg. 
It is important to also go into the files calling these and delete them there too. 


**### Set up New App.js File**

Continue to delete the boiler plate files and create a simple functional component that returns a <div> with an <h1> to make sure the page renders properly. 

```
import React from "react";
import "./App.css";

function App() {
    return (
        <div >
            <h1>‘Hello World’</h1>
        </div>
   );
}

export default App;
```

**### Set up Nav Bar with React-MDL** 

First go to React-MDL documentation: https://github.com/tleunen/react-mdl and install react-mdl. 

cd portfolio-blake
npm install --save react-mdl

Second, add the style sheet into the Head of index.html
`<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">`

Third, add the following two lines into src/index.js:
import 'react-mdl/extra/material.css';
import 'react-mdl/extra/material.js';

Check to make sure the site is still rendering properly. 

**### Import Layout Style from React-MDL**

1. Go to the React-MDL website to choose layout: https://tleunen.github.io/react-mdl/components/layout/ 
2. Copy the layout into the return section of the App.js. It is important to import the necessary components required for that layout from react-mdl.
            For example, I needed to import {Layout, Header, Navigation, Drawer, Content } from ‘react-mdl’;
3. Find and replace each of the number signs “#“ within the <a> tags to slashes “/“ in order to make react happy. (i.e.  <a href=“#“>Link</a> should be <a href=“/“>Link</a>

```
import React from "react";
import { Layout, Header, Navigation, Drawer, Content } from "react-mdl";
import "./App.css";

function App() {
    return (
        <div className="demo-big-content">
    <Layout>
        <Header title="Title" scroll>
            <Navigation>
                <a href=“/“>Link</a>
                <a href=“/“>Link</a>
                <a href=“/“>Link</a>
                <a href=“/“>Link</a>
            </Navigation>
        </Header>
        <Drawer title="Title">
            <Navigation>
                <a href=“/“>Link</a>
                <a href=“/“>Link</a>
                <a href=“/“>Link</a>
                <a href=“/“>Link</a>
            </Navigation>
        </Drawer>
        <Content>
                <div className="page-content" />
        </Content>
    </Layout>
        </div>
    );
}

export default App;
```

**### Build Components for Links**

Within the src folder, add folder components and within that add the following files: landingpage.js, aboutme.js, projects.js, contact.js
Each of these components will be very similar, so one sample is below. 

```
import React, { Component } from "react";

class Projects extends Component {
    render() {
        return (
            <div>
                <h1>Projects</h1>
            </div>
        );
    }
}

export default Projects;
```


**### Implement Routing**


1. Run npm install react-router-dom —save
2. In order to be able to use a router, it must be rendered at the root of the element hierarchy. So, inside index.js wrap the <App> component inside <BrowserRouter> as shown below.   Remember to import the necessary components from react-router-dom.

import React from "react";
import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import * as serviceWorker from "./serviceWorker";
import "react-mdl/extra/material.css";
import "react-mdl/extra/material.js";
import { BrowserRouter } from "react-router-dom";

ReactDOM.render(
<React.StrictMode>
<BrowserRouter>
    <App />
</BrowserRouter>
</React.StrictMode>,
document.getElementById("root")
);
serviceWorker.unregister();


3. Set up all routes in new class component Main.js

Both Switch and Route are route matching components. Use the Switch component to render the <Route> components. The way a <Switch> component works is that when it is rendered, it searches through its children <Route> elements to find the path that matches the URL it's looking for. Once it finds a match, it renders that <Route> and stops there. For this reason, it is important to put <Route>(s) with more specific (typically longer) paths before less-specific ones. In the case that the <Switch> component finds no <Route> matches, it renders nothing (null).

For the landing page, there is an exact path. However, for the rest of the components there is only path. 

import React from "react";
import { Switch, Route } from "react-router-dom";
import LandingPage from "./landingpage";
import AboutMe from "./aboutme";
import Projects from "./projects";
import Contact from "./contact";
 
const Main = () => (
    <Switch>
        <Route exact path="/" component={LandingPage} />
        <Route path="/aboutme" component={AboutMe} />
        <Route path="/projects" component={Projects} />
        <Route path="/contact" component={Contact} />
    </Switch>
);

export default Main;

4. Import the Main file in the App.js file and render it between the <Content> component from react-MDL. Additionally, must import {Link} from react-router-dom. This allows us to change the <a> tags to <Link to> tags. See below.
```
import React from "react";
import { Layout, Header, Navigation, Drawer, Content } from "react-mdl";
import "./App.css";
import Main from "./components/main";
import { Link } from "react-router-dom";

function App() {
    return (
        <div className="demo-big-content">
    <Layout>
        <Header title="Title" scroll>
            <Navigation>
                <Link to="/aboutme">About Me</Link>
                <Link to="/projects">Projects</Link>
                <Link to="/contact">Contact</Link>
            </Navigation>
        </Header>
        <Drawer title="Title">
            <Navigation>
              <Link to="/aboutme">About Me</Link>
              <Link to="/projects">Projects</Link>
              <Link to="/contact">Contact</Link>
            </Navigation>
        </Drawer>
        <Content>
                <div className="page-content" />
        </Content>
    </Layout>
        </div>
    );
}

export default App;
```

