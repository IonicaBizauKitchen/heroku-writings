This article gives an overview of [node-ws-test](https://github.com/heroku-examples/node-ws-test), a sample Node.js app
using the [ws](http://einaros.github.io/ws/) WebSocket implementation.

>note
> The code for this [demo application](https://github.com/heroku-examples/node-ws-test) is available on GitHub. Edits and enhancements are welcome. Just fork the repository, make your changes and send us a pull request.

## Prerequisites

If you're new to Heroku or Node.js development, you'll need to set up a few things first:

- A Heroku user account. [Signup is free and instant](https://api.heroku.com/signup/devcenter).
- [Heroku Toolbelt](https://toolbelt.heroku.com), which gives you git, foreman, and the heroku command-line interface.
- [Node.js](http://nodejs.org/), easily installed on Mac, Windows, and Linux with packages from [nodejs.org](http://nodejs.org/).

## About the Sample App

The behavior of this sample app is very simple: The server periodically sends messages to the browser over a WebSocket, and the browser renders each new message in the DOM. You can observe this by viewing the deployed sample app at [node-ws-test.herokuapp.com](https://node-ws-test.herokuapp.com/).

The [server](https://github.com/heroku-examples/node-ws-test/blob/master/server.js) is a Node.js app powered by [express 3](http://expressjs.com/guide.html), node's native [http](http://nodejs.org/api/http.html) module, and the [einaros/ws](https://github.com/einaros/ws/blob/master/doc/ws.md) WebSocket implementation. Express is used to serve the static frontend.

The [client](https://github.com/heroku-examples/node-ws-test/blob/master/index.html) has no dependencies. It makes use of the browser's native WebSocket functionality to establish a connection with the server.

## Running the App Locally

Clone the repo:

```term
$ git clone https://github.com/heroku-examples/node-ws-test.git
Cloning into 'node-ws-test'...
remote: Counting objects: 22, done.
remote: Compressing objects: 100% (15/15), done.
remote: Total 22 (delta 6), reused 20 (delta 5)
Unpacking objects: 100% (22/22), done.
Checking connectivity... done
```

Install dependencies with npm:

```term
$ cd node-ws-test
$ npm install
npm http GET https://registry.npmjs.org/ws
npm http GET https://registry.npmjs.org/express
npm http 304 https://registry.npmjs.org/ws
npm http 304 https://registry.npmjs.org/express
npm http GET https://registry.npmjs.org/ws/-/ws-0.4.31.tgz
... etc
```

The application's Procfile contains the single process you need to get up and running locally:

```term
$ cat Procfile
web: node server.js
```

Fire up the app with foreman:

````
$ foreman start
17:00:04 web.1  | started with pid 3999
17:00:05 web.1  | http server listening on 5000
17:00:05 web.1  | websocket server created
... etc
```

You should now have a node webserver running locally
at [localhost:5000](http://localhost:5000).

## Deploying to Heroku

Create a new Heroku app:

```term
$ heroku create
Creating boiling-bastion-2872... done, stack is cedar
http://boiling-bastion-2872.herokuapp.com/ | git@heroku.com:boiling-bastion-2872.git
Git remote heroku added
```

Enable websockets for your new app:

```term
$ heroku labs:enable websockets
Enabling websockets for boiling-bastion-2872... done
WARNING: This feature is experimental and may change or be removed without notice.
For more information see: https://devcenter.heroku.com/articles/heroku-labs-websockets
```

Push your app to Heroku:

```term
$ git push heroku master
Counting objects: 22, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (20/20), done.
Writing objects: 100% (22/22), 3.32 KiB | 0 bytes/s, done.
Total 22 (delta 6), reused 0 (delta 0)

-----> Node.js app detected
-----> Resolving engine versions
       Using Node.js version: 0.10.20
       Using npm version: 1.2.30
-----> Fetching Node.js binaries
-----> Vendoring node into slug
-----> Installing dependencies with npm
       npm http GET https://registry.npmjs.org/express
       npm http GET https://registry.npmjs.org/ws
       npm http 200 https://registry.npmjs.org/ws
       npm http GET https://registry.npmjs.org/ws/-/ws-0.4.31.tgz
       npm http 200 https://registry.npmjs.org/express
       ... etc
       Dependencies installed
-----> Building runtime environment
-----> Discovering process types
       Procfile declares types -> web

-----> Compiled slug size: 16.4MB
-----> Launching... done, v4
       http://boiling-bastion-2872.herokuapp.com deployed to Heroku

To git@heroku.com:boiling-bastion-2872.git
 * [new branch]      master -> master
 ```

Open your newly deployed app in the browser:

```term
$ heroku open
```

## Going Further

This demo app only scratches the surface of what is possible using WebSockets. For
a deeper dive into building Node.js apps using WebSockets, see [Geosockets](https://github.com/heroku-examples/geosockets),
a Node.js server and client that renders website visitors on a map in realtime using WebSockets
and the browser's Geolocation API.

## Additional Topics

For more information about using Node.js and WebSockets on Heroku, see the following articles:

- [Heroku Labs: WebSockets](https://devcenter.heroku.com/articles/heroku-labs-websockets)
- [WebSocket Security](https://devcenter.heroku.com/articles/websockets-security)
- [WebSockets Public Beta Blog Post](https://blog.heroku.com/archives/2013/10/3/websockets-public-beta)