# NoSleep.js

A fork of github.com/richtr/NoSleep.js which works as a Node module.

Prevents display sleep and enable wake lock in all Android and iOS web browsers.

## Installation

I'm not publishing this in the npm registry because it would make more sense for the upstream repo to do that eventually.

You can still install this fork using npm using this format:

    $ npm install BHSPitMonkey/NoSleep.js

## Usage

Create a new NoSleep object and then enable or disable it when needed as follows:

``` javascript
var NoSleep = require("nosleep");
// Or ES6-style:
// import NoSleep from "nosleep";

var noSleep = new NoSleep();

function enableNoSleep() {
  noSleep.enable();
  document.removeEventListener('touchstart', enableNoSleep, false);
}

// Enable NoSleep.
// (must be wrapped in a user input event handler e.g. a mouse or touch handler)
document.addEventListener('touchstart', enableNoSleep, false);

// ...

// Disable wake lock at some point in the future.
// (does not need to be wrapped in any user input event handler)
noSleep.disable();
```

## License

Same as upstream:

MIT. Copyright (c) Rich Tibbett
