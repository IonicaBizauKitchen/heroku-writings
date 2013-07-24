# Managing Modules

```
cd my-node-app

# Install a module locally and add it to package.json dependencies
npm install express --save

# Install a module locally and add it to package.json devDependencies
npm install express --save-dev

# Remove any modules that are no longer in package.json
npm prune
```


## Node Versions

[Node Version Manager](https://github.com/creationix/nvm) is a simple bash script to manage multiple active node.js versions.



Starting with Node 0.6, since require() can read and parse JSON files automatically, you can leverage it to easily introspect package.json:

require('my-module/package').name

npm docs grunt
npm docs express

npm view express


outlet master $ npm info request version
npm http GET https://registry.npmjs.org/request
npm http 200 https://registry.npmjs.org/request
2.16.6


Starting with Node 0.6, since require() can read and parse JSON files automatically, you can leverage it to easily introspect package.json:


npm docs express
npm view express
npm info express repository

## Callbacks

"Write small modules that each do one thing, and assemble them into other modules that do a bigger thing. You can't get into callback hell if you don't go there." - [Isaac](http://twitter.com/izs)

http://callbackhell.com/