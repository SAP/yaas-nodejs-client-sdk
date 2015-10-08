# yaas.js
## Node.js module for hybris as a Service (Yaas)

### Overview
This node.js module simplifys the access to the YaaS REST API. It handles authentication via OAuth2, replacement of expired tokens as well as automated retry of failed requests due to expired tokens. Knowledge of URLs is not necessary, every action has its own function. Currently only API calls that were needed for hybris labs prototypes are implemented.

### Requirements
This module makes use of JavaScript features that are still considered experimental (i.e. [Promises](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Promise)). You therefore need a more recent version of node.js that supports ECMAScript 6 (Harmony).

### Usage
You can include this module as a Git submodule into your project. 

Include the module like this in your node.js code (assuming the submodule folder is called `yaas.js`):

	var yaas = require('./yaas.js/yaas.js');

The various CaaS services are used for namespacing like

	yaas.product.getProduct(theProductId)
	yaas.cart.deleteCart(cartId)
	...

### Things to clarify
* General architecture
* Handling of HTTP status codes
* Structure of returned object used for *all* functions
* Better namespacing / avoid duplicate naming in function calls (e.g. yaas.cart.deleteCart() becomes yaas.cart.delete())
* Development principles (git-flow, branches, Pull Requests, unit tests, ...)
* Release on GitHub