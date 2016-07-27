# 1.1 Wiring Together Views
* take static files and take it and bring it into alive angular js.
* Take unique code and separate them into their own templates
* angular routes allow us to map URLS to use templates so everytime the route changes, the view changes with it
* four steps to routing happy
	1. use ngview
	2. loading ngRoute library
	3. importing ngRoute module
	4. define routes
	* ex. angular.module("NoteWrangler", [ngRoute])

# 1.5 Logic in our Routes
* $http is an async request to the server
* can also associate controllers with routes
* you can use $routeParams to pull things out and utilize them
	* :var is a var
	* then can do $routeParams.var to get it

# 2.1 $scope
* so we can do this.header = "note title"
* then call it {{card.header}}
* or we can do $scope.header = "note title"
* then call it as {{header}}
* scope attaches it directly to the controller.
* inherit parents scope, can pass in {} as scope to the directive and it'll be isolated, meaning do not interact with other scopes
* if you set a header var on a child, it's also setting that header var on the parent
* three options to bind characters to a scope
	1. @
	2. = (two way binding, so it changes in one place it changes in the other)
	3. ampersand
* scope in directive allows you to create an isolate scope
* $scope lets you set values as properties on the scope

# 2.10 Link
* link function is run after directive is compiled and linked up.
* best spot to do DOM manipulation or logic functionality.
* link has an element parameter, scope and element so now you can use element selector so you're not searching entire DOM
* use library to change body from markdown to HTML (if you wanna do this)

# 3.1 A Service for Our Data Calls
* Services hold functions that are responsible for connecting and fetching data.
* after creating a service you can use it inside of a controller or directive
* five recipes for services:
	1. Value
	2. Factory - share functions and objects across application
	3. Service
	4. Provider - like factory but allows for configuration
	5. Constant
* ex. angular.module("NotesWrangler").factory("Note", function NoteFactory() {...});

# 3.4 A Service for an Outside API
* value is used to share a value throughout your app repeatedly
* factory shares methods and objects
* service is an instance of methods and objects
* provider shares methods and objects but with config
* constant shares value within application config

# 3.7 Providers
* all providers have a $get, where you return an object and inject services

# 3.10 $resource
* ngResource is not included with angular core by default

# 4.1 Helping Child and Parent Communicate
* reusable directives

# 4.6 Filters
* such a thing as a filter filter, which will take in an array, and filter through the array and return a new array

# 4.10 External Library Directive
* must wrap external libraries in a directive, then use that directive
* ex. -> bootstrap.js put it in vendor directory and insert
* create directive, since you want to override html you want to name it the same thing
* 

