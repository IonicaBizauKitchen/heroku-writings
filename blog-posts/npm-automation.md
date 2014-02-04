Using automation tools like Grunt and Gulp in the Heroku Build process

# Automating Node.js Tasks on Heroku using Grunt, gulp.js, and npm

As the npm ecosystem continues to grow, so do the options for automating the development and build process. Grunt is by far the most popular build tool in the Node world today, but minimal new tools like [gulp.js](http://gulpjs.com/) and [plain old npm scripts](http://substack.net/task_automation_with_npm_run) are also attractive options with lighter footprints. In this post, I'll highlight how to integrate these tools into your node apps in a way that fits nicely with the Heroku build process.

## npm Scripts Hooks

When you deploy a node app to Heroku, the `npm install --production` command is run to ensure your app's npm dependencies are downloaded and installed. But the command does something else too: It runs any [npm script hooks](https://npmjs.org/doc/misc/npm-scripts.html) that you've defined in your package.json file, such as `preinstall` and `postinstall`. Here's a sample:

```json
{
  "name": "my-node-app",
  "version": "1.2.3",
  "scripts": {
    "preinstall": "echo here it comes!",
    "postinstall": "echo there it goes!",
    "start": "node index.js",
    "test": "tap test/*.js"
  }
}
```

These scripts can be inline bash commands or they can refer to [command-line executables](https://github.com/substack/blog/blob/742794366c89622b0a7ce2ee848d1edd92d94651/npm_run.markdown#the-scripts-field). You can also refer to other npm scripts from within a script:

```json
{
  "scripts": {
    "postinstall": "npm run build && npm run rejoice",
    "build": "grunt",
    "rejoice": "echo yay!",
    "start": "node index.js"
  }
}
```


http://stackoverflow.com/questions/15890076/how-to-setup-gruntfile-to-use-compass-sass-on-heroku