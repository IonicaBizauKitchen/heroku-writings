- add "track node version" to trello board


Heroku Postgres requires ssl connections, which are off by default in the pg npm package. Instructions on enabling this should be included. https://github.com/brianc/node-postgres/wiki/Client#new-client_object_-config--client

var pg = require('pg').native; will use libpq for connecting to postgres, which allows the app to use SSL. As Heroku Postgres requires SSL, I suggest recommending using the native pg adapter. https://github.com/brianc/node-postgres/issues/25#issuecomment-1033547

Please add `if (err) throw err;` to the pg example. The error client.query('...', function(err, result) {
^
TypeError: Cannot call method 'query' of null

is very misleading.



buildpack-env-arg


Add some info about why node-logfmt is being used in the sample app. Love, Zeke (via Morten)


process.env.PORT is a string, and some libraries like Socket.IO require this to be a number:

var io = require('socket.io').listen(Number(process.env.PORT));

https://github.com/LearnBoost/socket.io/issues/276