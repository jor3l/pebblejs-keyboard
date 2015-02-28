# PebbleJS Keyboard

PebbleJS keyboard is a simple attempt to get a working keyboard in the watch. 

The idea is to provide a simple and fast input method for quick replies, sing ups or validations (code validation e.g).

## Getting started

The easiest way to use the keyboard is in [CloudPebble](https://cloudpebble.net), just copy the contents of the pebble-keyboard.js to a new asset in your project.

In your main.js or the file that needs the keyboard, do a simple: 

````js
var Keyboard = require('pebblejs-keyboard'); // Asuming the file is named pebblejs-keyboard.js
```

The variable Keyboard will have the module, you can create now as many keyboard instances you like, I recommend using only one to use less memory and keep it as simple as possible.

To initialize your keyboard, simply call `new Keyboard(WindowObject)`, passing a Window Object set to `fullscreen: true` to the Keyboard module, this window is where the keyboard will be displayed, you can set a new window later by calling `Keyboard.window(WindowObject)`.

````js
var myKeyboard = new Keyboard(window);
```

After creating the keyboard, hook a *text* event to receive the user input:

````js
myKeyboard.on('text', function(input) {
	console.log('user typed: ' + input)
});
```

Now you can display the keyboard to the user at any time:

````js
myKeyboard.show();
```

You can also hide the keyboard by calling `hide()`.

## Using the Keyboard

For the user, I tried to make the keyboard reeeeally simple using the 3 keys on the right like this:
	
	* Switch from letters to numbers or symbols by long-pressing the down button
	* Erase a character by long-pressing the up button
	* Change the character with up/down
	* Select a character with the select button (middle)
	* Submit the input by long-pressing the select button (middle)
