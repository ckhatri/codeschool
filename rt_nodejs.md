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
* 