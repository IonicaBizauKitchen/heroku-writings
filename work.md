## App Gallery

Together with the Partner team and [Eric Holmes](http://ejholmes.github.com/) from Luminosity Group, we're building a gallery of apps running on Heroku, and using the Heroku API to collect metadata about those apps, like what language they're built in, how many dynos they're running, and what addons they're using. The end result will be an open webservice that other Heroku properties can consume. Some examples:

- partners.heroku.com: display a portfolio of apps created by that agency.
- success.heroku.com: display curated case studies of our more interesting and successful apps.
- addons.heroku.com: showcase apps using a particular addon or addon "recipe".
- dashboard.heroku.com: display apps as products/projects with individual identities.

## Node Builpack

The last release of the Node Buildpack was eight months ago. How long is eight months in Internet time?

Last week David and I spent some time inspecting the Node Buildpack, [cutting new releases](https://github.com/heroku/heroku-buildpack-nodejs/pull/31), and triaging Github issues. Though shell scripting is not my number-one hobby, I'm excited about the opportunity to help maintain a vital piece of Heroku's officially-supported polyglot offering.

## Anvil (doesn't exist)

I heard three people at Waza say they don't use Heroku for their more specialized apps because they don't know how to handle binary dependencies. Anvil is already here, but its [lack of documentation](https://devcenter.heroku.com/articles?q=anvil) has kept it from entering the public consciousness. With proper branding and docs behind it, Anvil will open new doors to userspace platformization.

## Other Important Things

- [panHeroku Nav](https://github.com/heroku/boomerang#readme)
- EU Launch Page
- A Buildpack Directory, because there are a [bunch](http://buildpacks.heroku.com/)
  of [varying](https://devcenter.heroku.com/articles/third-party-buildpacks) buildpack
  [lists](https://devcenter.heroku.com/articles/buildpacks) out [there](https://github.com/buildpacks).
- A CLI Plugin Directory: A minimalist revival of the now-defunct herocutter. In it's simplest form this could be a list
  of github repos, with some CLI integration like `heroku plugins:list` and `heroku plugins:search foo`.
- [Icon Build Pipelines](https://github.com/zeke/miyagi/blob/font-pipeline/app/models/font.rb).
- [The emerging Directory Design Pattern](https://basecamp.com/1764621/projects/2224615-design-rodeo/messages/8991465-filtering-uis-are)
