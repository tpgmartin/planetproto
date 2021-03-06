The 'function prototype'
------------------------

Every function in JavaScript has a special property called ‘__prototype__’.

```js
function Alien(){
}

Alien.prototype
```

As confusing as it may sound, this ‘__prototype__’ property is not the real prototype (__\_\_proto\_\___) of the function. 

```js
Alien.__proto__ === Alien.prototype //=> false
```

This of course generates a lot of confusion as people use the term '__prototype__' to refer to different things. 
A good clarifirobotion is to always refer to the special '__prototype__' property of functions as '__the function prototype__', never just '__prototype__'.

**This ‘__prototype__’ property points to the object that will be assigned as the prototype of instances created with that function when using '__new__'.**

Confusing? This is easier to explain with an example:

```js
function Alien(name) {
	this.name = name;
}

// the function Alien has a prototype property
// we can add properties to this function prototype
Alien.prototype.kind = 'alien'

// when we create a new object using new
var zippy = new Alien('Zippy');

// the prototype of the new object points to alien.prototype
zippy.__proto__ == Alien.prototype //=> true

// in the new object we have access to properties defined in Alien.prototype
zippy.kind //=> alien
```

Here is a [diagram showing this relationship](https://docs.google.com/drawings/d/1AKJcvxs0t3iGtqkRV8rFAWlo7tojkOSwjfhr1NWaTb0/pub?w=889&h=482)

That is mostly everything there is to know about the JavaScript object model. Understanding how __\_\_proto\_\___ and __function.prototype__ are related will give you countless hours of joy and satisfaction, or maybe not.

Challenge
---------

- Define an 'Robot' function constructor
- Create two instances of Robot: 'robby' and 'cranky'
- Both robby and cranky should respond to 'parts' and 'capabilities', these should be empty arrays at first
- Claim the result of robby.parts
- Claim the result of cranky.parts
- Claim the result of robby.capabilities
- Claim the result of cranky.capabilities
- Add 'core' to robby.parts, cranky.parts should still be empty
- Add 'fly' to robby.capabilities, after doing that cranky.capabilities should also have 'fly' without adding to it directly
- Claim the result of robby.parts
- Claim the result of cranky.parts
- Claim the result of robby.capabilities
- Claim the result of cranky.capabilities

Boilerplate
-----------

A file 100.js with the necessary boilerplate has been created for you.


