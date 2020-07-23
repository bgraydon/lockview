# Lockview
A small JS library to generate parametric SVG images of locks and keys, animate them and integrate onto web pages.  Released as a supporting tool for my DEF CON 28 talk on key space hacking: https://defcon.org/html/defcon-safemode/dc-safemode-speakers.html#Graydon. 

# Beta
The version currently released is very rough around the edges.  I'm primarily using it to aid in my DEF CON presentation at the moment.  Polishes to come after DEF CON.

# Examples
The majority of people will probably just want to play with the examples rather than use this as a library.

Example source code is in the /examples folder.  Live examples are online:

### Standard non-mastered system:

https://ggrsecurity.com/personal/~bgraydon/lockview/examples/schlage-nonmastered.html

### Mastered system:

https://ggrsecurity.com/personal/~bgraydon/lockview/examples/schlage-mastered.html

### Interchangeable Core:

https://ggrsecurity.com/personal/~bgraydon/lockview/examples/ic.html

### Construction Keyed Lock:

https://ggrsecurity.com/personal/~bgraydon/lockview/examples/construction.html

### Bump Key (note - inertial physics not simulated):

https://ggrsecurity.com/personal/~bgraydon/lockview/examples/bumpkey.html

### Lock Impressioning Minigame:

https://ggrsecurity.com/personal/~bgraydon/lockview/examples/impression.html

# Using the Library
Lockview is a javascript library that allows interactive images of locks and keys to be incorporated into any web page.  It requires SVG.js: https://svgjs.com/docs/3.0/

All relevant functions and objects are under the "lockview" object.  

To add a lock to a webpage, create a container div or other HTML element with some id:
`<div id='lock0'></div>`

And _after the page has loaded_ call the `lockview.addLock` function:

```
lockview.addLock(
  'lock0', // HTML Container element ID
  lockview.schlageLockspec, // Information about the lock dimensions
  lockview.defaultViewOpts, // What controls should be visible, styling, etc
  [2,4,5,3,1], // Key Code
  [[2],[4],[5],[3],[1]], // Shear lines 
  "KEY" // Text stamped on the bow of the key
);
```

The return value of `lockview.addLock` is a JS Object with fields and functions that can be used to manipulate the lock / key after its creation.

Much more complete documentation is to come.
