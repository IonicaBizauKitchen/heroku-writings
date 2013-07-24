outlet master $ npm info request version
npm http GET https://registry.npmjs.org/request
npm http 200 https://registry.npmjs.org/request
2.16.6


Starting with Node 0.6, since require() can read and parse JSON files automatically, you can leverage it to easily introspect package.json:


npm docs express
npm view express
npm info express repository

https://npmjs.org/doc/json.html#repository

https://coderwall.com/p/obu1yw?i=7&p=1&q=sort%3Ascore+desc&t%5B%5D=node


- [node debugger screencast](https://vimeo.com/19465332)
- http://nodejs.org/api/debugger.html
- https://github.com/dannycoates/node-inspector


"Write small modules that each do one thing, and assemble them into other modules that do a bigger thing. You can't get into callback hell if you don't go there."

http://callbackhell.com/