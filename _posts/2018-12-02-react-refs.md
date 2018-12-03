---
title: React Refs
date: "2018-12-02"
---

### What is a `ref` in React?
_Stumble with me through React, a web browser and the fuzzy grey area between._

#### Background ####
Recently I made a decision to read through all of the <a href="https://reactjs.org/docs/hello-world.html">React documentation</a> to more deeply understand the framework and to try and pick up any basics I might have missed or glossed over. Though I have worked with React a bit professionally, I had not ventured into the documentation until I needed to know something specific. In hindsight I wish I read through them sooner because they are fantastic.

That said, while reading I came to the notes on <a href="https://reactjs.org/docs/refs-and-the-dom.html">Refs and the DOM</a> and wondered why anyone would need this functionality. At its core, React is an abstraction of the native DOM elements that your browser can render along with their attributes and various functions. These "elements" describe <em>what</em> you want React to render, but they themselves are _not_ elements. More on that here: <a href="https://reactjs.org/docs/rendering-elements.html">Rendering Elements</a> and <a href="https://reactjs.org/blog/2015/12/18/react-components-elements-and-instances.html">React Components, Elements and Instances</a>.

Using this abstraction with React you can manipulate the state of the DOM elements that you want React to render, using `props` and `state`. These are the foundations and building blocks of React.

#### The Confusion

Why would I need a `ref`erence to an _actual, live, real_ DOM element when React abstracts all of that behavior for me and provides a means for manipulating it. Couldn't I just change `props` and `state` to get the behavior I want in every possible scenario?

I thought, surely something like focusing an `input` element in the DOM is as simple as passing a prop to that Element that determines whether or not it should be focused, or blurred.

#### Let's do an Experiment!

Write a React Component that renders an `input` and ensure that at that the `input` is in `focus`. <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus">Related docs.</a>

--- 


```javascript
import React from "react";
import ReactDOM from "react-dom";

class CustomInput extends React.Component {
  render() {
    // What to do with the input element below?
    return <input />;
  }
}

function App() {
  return (
    <div>
      <p>A glorious input:</p>
      <CustomInput />
    </div>
  );
}


const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);
```

<a href="https://codesandbox.io/embed/zn0486yjl">Try it out</a>



      
The docs describe <code>ref</code>s as an "escape hatch" and then go on to provide a few example Escape from <em>what</em>, I asked? 
      
You're probably thinking that "Every React developer worth their shorts knows about <code>ref</code>s" and you may well be right. 
However, a few days ago I had no idea what they were or why they were useful.

#### The Problem