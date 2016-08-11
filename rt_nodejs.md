# 1.1 Intro to Node.js
* node provides wrapper around v8 JS runtime.
* ex. ad servers, websocket servers, fast file upload client
* any real-time data apps
* node.js is not a web framework, and it is NOT multi-threaded GOD BLESS
* when complete -> do this is called a callback
* ex nonblocking code
	* func(param, callbackfunc() {
		console.log(contents);
	});
	* console.log(doing other stuff);

# 2.1 Events
* events in dom, dom triggers events ex. click, submit, hover
* request listener function is automatically added to request event

# 3.1 Streams
* when writing applications on network access, must keep an eye out for how data is being transferred back and forth
* if we can get data chunk by chunk, we can manipulate as soon as we get those chunks
* streams are readable and writer
* request is readable, response is writable
* so do a while loop to read a chunk from the request
* pipe allows you to read from a readable stream, then send it to a response stream as a helper method
* request.pipe(response), will simply write the request to the response.

# 4.1 Modules
* npm is the package manager for node
* create package.json file, which specifies dependencies 
* npm install will look in package.json and try to fetch and install dependencies and create the node modules directories
* semantic versioning, 1.8.7 -> 1 is major, 8 is minor, 7 is patch
* 