---
title: React from Scratch - Part 3
date: "2019-1-26"
---

[React](https://reactjs.org/) is a framework from Facebook that let's us build user interfaces. It is know for its ability to efficiently manage changes to the DOM.

**Part 3 - TL;DR;**

- Install React and ReactDOM
- Write some React ⚛️ !!! 
- Debugging
- JSX
- Summary

### Install React and React DOM

Let's add `react` and the `react-dom` node packages as primary dependencies:

```terminal
$ npm install react react-dom
```

### Write some React!

Let's modify `src/index.js` to create a React Component and render it into the DOM with ReactDOM:

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  React.createElement('h1', null, 'Hello world!'),
  document.getElementById('root')
);
```

I know what you're saying, this doesn't make use of that JSX syntatic sugar. We'll get to that in a bit.

Now update `dist/index.html` and add a `<div>` into which to render our React Components:

```html
<!doctype html>
<html>
  <head>
    <title>Hello World!</title>
  </head>
  <body>
    <script src="main.js"></script>
    <div id="root">
    
    </div>
  </body>
</html>
```

Re-run webpack, and check refresh your browser:
