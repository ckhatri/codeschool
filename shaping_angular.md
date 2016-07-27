# 1.1 Ramp Up
* What normally happens when you click a link is a request is sent to the server, server gives back assets and then browser loads page
* responsive, what happens is that when you click on something, only the info needed to update the page is sent
* a **directive** is a marker on HTML tags that tells angular to reference or run JS code
* **modules** - where we write pieces of angular, define dependencies, easy to maintain and test.
* var app = angluar.module('store', []), store is application name, [] dependencies
* add ng-app to html tag, it's a directive to create an angular application by running the module you set it to
	* ng-app = "store"
* **expressions** - allow you to insert dynamic values into HTML {{something}}

# 1.3 Index HTML setup
* **controllers** - help us get data onto the page
	* this is where we define our applications behavior
	* ex. app.controller("StoreController", function() {

	});
	* in the html you add ng-controller to tag, <div ng-controller="StoreController as store">
	* attached store controller to that div, store is the alias.
* wrap JS in a closure, it's a good habit
* scope of controller is only in that DOM element

# 1.5  Built-In Directives
* ng-show directive basically says only show up if this value is true
* ng-repeat is basically a for each loop
	* ex. ng-repeat="product in store.products"
* **directives** - html annotations that trigger javascript behavior
* **modules** - where application lives
* **controllers** - where we add application behavior
* **expressions** - how values get displayed in page

# 2.1 Filters and a New Directive
* pipe says take first expression and put it into the second one
* example of filter is currency
* can't do img src = {expression}, html does src first not expression need to use ng-src

# 2.6 Tabs Inside Out
* ng-click directive takes an expression 
* two way data binding means that an expression are re-evaluated when a property changes.
* lots of logic is bad in the html, make a new controller

# 3.1 Forms and Models
* ng-model binds form element value to the property
* can use ng-model for check boxes or buttons

# 3.5 Accepting Submissions
* better to do initialization in a controller, but can use ng-init.
* ng-submit allows you to call a function when a form is submitted.

# 3.8 Form Validation
* can simply add required
* $valid is angular valid form, built in?
* certain fields like email have two classes .ng-invalid/valid and ng.dirty/clean and it auto updates for you
* because you know these class names you can set CSS to them

# 4.1 Directives
* we're going to have multiple pages that want to reuse HTMl code
* ng-include lets you include a file 
	* ex. ng-include = "'top.html'"
	* now what happens is you get index.html -> ajax request to get the top.html file once you hit the ng-include
* why write directives?
* directives allow you to write html that expresses behavior of your application.
* template expanding directives
	* define custom tag or attribute to expand or replace
	* can include controller logic if needed
* directives can be used for:
	* expressing complex UI
	* calling events and registering events
	* reusing common components
* how to build custom directives
	* app.directive('title', function() {
		return {
			restrict: 'E' <- type of element (E for element)
			templateUrl: 'product-title.html' <- url of template;
		};
	});
* use element directives for UI widgets and Attribute Directives for mixin behaviors
* **When writing an AngularJS application, you should be able to understand the behavior and intent from just the HTML**

# 4.5 Directive Controllers
* how do you move a controller into a directive?
	* first do controller: function() {
		funtionality goes here
	}
	* controllerAs: 'alias'

# 5.1 Dependencies 
* all our controllers and directives are mixing together, lets clean up code
* lets say a module is every directive dealing with store products
* so create the module than make the original module, depend on it !dependencies
* best to split modules around functionality
	* app.js - top level module attached via ng-app
	* products.js - all functionality  for products and only products

# 5.3 Services
* services give you controller additional functionality, such as log or fetching json data
* services built in start with $
* must state what services the controllers need, dependency injection
* 