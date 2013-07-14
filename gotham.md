# Crowdsourcing Heroku's Node Buildpack

Description
-----------

Heroku is a polyglot platform, supporting any programming language

Heroku's open-source buildpacks enable developers to run practically anything, including Node.js. In this talk I'll discuss the tools and technique I use to help the community determine the future of the Node buildpack.

Heroku's open-source buildpacks enable developers to develop and deploy apps in any language, including JavaScript. In this talk I'll discuss the tools and techniques I use to help let the open-source community determine the future of the Node buildpack.

The buildpacks are where all the magic happens in the deploy process.

These buildpacks are open-source and available on Github. If you have a change that would be useful to all Heroku developers, we encourage you to submit a pull request

When you `git push heroku`, the slug compiler prepares your code for execution. At the heart of the slug compiler is a collection of scripts called a buildpack.
