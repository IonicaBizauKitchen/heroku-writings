## Node's Event Model

Node's event-driven asynchronous design allows a single node process to handle multiple requests concurrently. Node's evented architecture is similar to and influenced by systems like Ruby's [Event Machine](https://github.com/eventmachine/eventmachine) and Python's [Twisted](http://en.wikipedia.org/wiki/Twisted_(software)), but node takes the event model a bit further by presenting the [event loop as a language construct](http://nodejs.org/about/) instead of as a library. For many apps, a single node process is more than enough to handle the request volume.

For more heavily trafficked node apps running on multi-core systems (like those on Heroku), it's possible to acheive greater concurrency by taking advantage of [node core's cluster module](http://nodejs.org/api/cluster.html), which automatically load-balances incoming connections across multiple processes. This allows you to create child processes that share server ports and make use of all available CPUs.

## Using Cluster

If you have an existing node app and wish to update it to use cluster, you'll need to update your app's entry point script, e.g. `server.js` or `index.js`. Here's a simple cluster usage example from [node's docs](http://nodejs.org/api/cluster.html)

> warning
> Node Cluster's [stability index](http://nodejs.org/api/documentation.html#documentation_stability_index) is currently set to *1: Experimental*. Always test your changes in a staging environment before deploying to your production application.

```js
var cluster = require('cluster');
var http = require('http');
var numCPUs = require('os').cpus().length;

if (cluster.isMaster) {
  // Fork workers.
  for (var i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  cluster.on('exit', function(worker, code, signal) {
    console.log('worker ' + worker.process.pid + ' died');
  });
} else {
  // Workers can share any TCP connection
  // In this case its a HTTP server
  http.createServer(function(req, res) {
    res.writeHead(200);
    res.end("hello world\n");
  }).listen(8000);
}
```

The above code represents the vanilla approach to using cluster, but a number of [cluster-related modules](https://npmjs.org/browse/keyword/cluster) are available on npm, many of which aim to abstract away the implementation details of node-cluster and make it easier to use.

## Related Articles

- [Dyno Size](https://devcenter.heroku.com/articles/dyno-size)
- [Scaling: Understanding Concurrency](https://devcenter.heroku.com/articles/scaling#understanding-concurrency)