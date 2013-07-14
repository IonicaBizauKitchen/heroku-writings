This weekend I had the great pleasure of attending [State of the Map US](http://stateofthemap.us/), a conference centered primarily around the [Open Street Map](http://en.wikipedia.org/wiki/OpenStreetMap) project. Many happy Heroku customers were to be found, and Postgres/PostGIS is a favorite technology among the GIS community. One particularly awesome Heroku customer I encountered was [Seth Fitzsimmons](http://www.stamen.com/studio/seth), Director of Technology at [Stamen](http://www.stamen.com), an SF design studio that does a lot of influential cartography and data visualization work.

Seth shared some great feedback about our product, and some interesting ideas too. Now, Herokai, I share it with you...

Seth's Gripes
-------------

> Monitoring on Heroku is hard.

> How do I know when to scale my dynos?

> It's hard to run apps with weird dependencies.

Seth's Ideas
------------

> I wish I could install debian packages, kind of the way Travis does, but I understand that it doesn't make sense to give root access in LXC containers.

> Create a homebrew buildpack to compose with other buildpacks. Precompile the bottles and have the buildpack download them. Homebrew runs unprivileged, and lets you set your own prefix. On Heroku it would be `/app` or `/app/vendor`

My Takeaways
------------

Seth's feedback echoes what I hear from many customers:

- Seth suggested that he and Stamen are getting more value out of the platform than they're paying for, and that he kinda feels bad about it. Customers want to pay us, but by following the [12 Factors](http://12factor.net/) and building small, composable webservices, they often end up with a bunch of single-dyno apps and a monthly bill that is disproportionately small compared to the value they're getting from us. We need a pricing model that works for companies running small yet legitimate microservices.

- Customers need more visibility into app resource consumption, so they can make informed decisions about when and how to scale. This has become increasingly relevant since the introduction of 2X dynos.

- Customers realize that heroku can run "anything", but they're pretty much on their own. Seth tried to use Vulcan to compile Cairo (a dependency of [node-canvas](https://github.com/LearnBoost/node-canvas)) but [hit some snags](https://github.com/mojodna/heroku-buildpack-nodejs#cairo-branch). To work around it, he compiled the dependencies on a local VM installation of Ubuntu, then [copied the binaries to S3](https://github.com/mojodna/heroku-buildpack-nodejs/blob/cairo/bin/compile#L204-L207). Though [Vulcan](https://github.com/heroku/vulcan), [Anvil](https://github.com/heroku/anvil), [Hammer](https://github.com/hone/hammer), [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) are powerful tools, their lack of documentation and/or "productization" has hindered their adoption.

