# StraightJS
## The Anti-framework

(under construction)

No "patterns.”

No decorations.  You stay out of our code, we stay out of yours.

No convention.  No configuration.

No views.  Write your own.

No components.  No modules.  No "pods" or "packages" or "controllers.”  You say you like them, but you don’t.

##Features

###Init

Pick your own tiny variable name.

```
     window._s = new Straight();
```

###Invoke

Safely invoke a method on another object.  That's decoupled enough!

```
     var result = _s.invoke(object, "someFunction", [arg1, arg2]);
```

###Broadcast & Listen

Talk to anyone, listen to anyone.  No actions bubbling up or whatever bubbling down.  Ride the straight talk express.
```
     // register homeObj to receive "phone" messages
     _s.listen("phone", homeObj, "onMessageReceived");

     // ET phone home, register callback for home phone ET
     _s.broadcast(ETObj, "phone", "onCallback", someData);
```

###Set, Get, Remove

Well, an equals sign would be better, but at least you can traverse nested JSON objects and arrays with RESTful paths.  Convenient?  Peculiar?  We don’t know.

```
     _s.set(someObj, 'path/to/var', value);
     _s.get(someObj, 'path/to/var');
     _s.remove(someObj, 'path/to/var');

```

###Observe

Call our set() function or don’t.  It’s your life.  But if you do call set() other code can react.  A couple wildcards let you listen to many things at once:
```
		// @@@ means "all descendents"
		_s.observe(someObj, "path/to/@@@", this, "onDataChanged");

		// @ means "any property or index"
		_s.observe(someObj, "array/@/propertyName", this, "onDataChanged");

```

And you can use regular expression syntax, too:

```
		_s.observe(someObj, "api/on[^\/]*", this, "onInterfaceChanged");     
```
We've heard it's really cool.

Plug an “adapter” or whatever into your JSON object and drive changes from anywhere.  Just don’t _tell us about it_ (link TBD).

##Want to get started?

Straight.js.  Simple, immature, unminified.  You hate it.  You can get it from the src folder.

##Want to install it as a module?  I guess we can’t stop you.

     (TBD...)
     npm install straightjs
     bower install straightjs

##How about a full application stack?

Fabulous!  Let us know when you’re done.

The following bon vivants seem to get along well:

     Node.js + Express.js + Locomotive.js + Hogan.js ——> Straight.js + jQuery

(Just serve yourself a template and don’t forget to water it.)

We’re trying it out [here](https://github.com/alloplastic/Choreo).

##Client-side SPA?

Watch your mouth.  What about plain Node/Express as the server and Straight.js + Pure.js + jQuery on the client?  Intriguing!  Why are you just sitting there?

#Straight.js#
##The framework that stays out of your bedroom

Want speed?  Wait two years and buy a new PC.

Want documentation?  [Write some](https://github.com/alloplastic/StraightJS/wiki).

Want scalability?  Instantiate Straight several times.

Want these instances to talk to each other?  Instantiate another one.

Extensibility?  Subclass your own thing, or just stick some functions on ours.  This isn’t C++.

```
	var _Choreo = function() {
		this.__proto__.__proto__ = new Straight();
	}

	_Choreo.prototype = {...}

     var _c = new _Choreo();
```

Don't ask us.  We didn't design the language.