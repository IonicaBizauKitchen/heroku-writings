# zeke.next

A sketch of my thoughts on the Heroku of today and tomorrow, and how I fit into it.

## App Gallery ()

### Role: Product Management and Design
### Co-Conspirators: Nicolas, Abe, Peter Chapman, and Eric Holmes.

Together with the Partner team and [Eric Holmes](http://ejholmes.github.com/) from Luminosity Group, we're building a gallery of apps running on Heroku, and using the Heroku API to collect metadata about those apps, like what language they're built in, how many dynos they're running, and what addons they're using. The end result will be an open webservice that other Heroku properties can consume. Some examples:

- partners.heroku.com: display a portfolio of apps created by that agency.
- success.heroku.com: display curated case studies of our more interesting and successful apps.
- addons.heroku.com: showcase apps using a particular addon or addon "recipe".
- dashboard.heroku.com: display apps as products/projects with individual identities.

## Node Builpack

### Role: Development and Maintenance
### Co-Conspirators: Terence, Kenneth, Michael Friis, David Dollar.

The Node Buildpack has been neglected for 8 months. David and I spent the last week dissecting the Node buildpack, [cutting new releases](https://github.com/heroku/heroku-buildpack-nodejs/pull/31), and triaging Github issues.

<!-- https://dataclips.heroku.com/hlxqofowidhnoqievnjfsmsoryyp -->

## Anvil

### Role: Design and Promotion
### Co-Conspirator: Ryan Daigle

I heard three people at Waza say they don't use Heroku for their more specialized apps because they don't know how to deal with binary dependencies. Anvil is already here, but its [lack of documentation](https://devcenter.heroku.com/articles?q=anvil) has kept it from entering the public consciousness.

The [current Devcenter advice for packaging binary dependencies](https://devcenter.heroku.com/articles/buildpack-binaries) is to use vulcan, and the Node Buildpack is using vulcan.

## Buildpack Directory

### Role: Design and Product Management
### Co-Conspirators: Michael Friis, Max, David

- Find out how this list has been maintained: https://devcenter.heroku.com/articles/third-party-buildpacks
- http://buildpacks.heroku.com/
- https://github.com/buildpacks

## Heroku CLI Plugin Directory

### Role: Design and Product Management
### Co-Conspirators: Keith, Wesley

A minimalist revival of the now-defunct herocutter. In it's simplest form this could be a list
of github repos, with some CLI integration like `heroku plugins:list` and `heroku plugins:search foo`.

## The Directory Design Pattern

### Role: Development, Design
### Co-Conspirators: Raul Barroso, Max, Raul Murciano

https://basecamp.com/1764621/projects/2224615-design-rodeo/messages/8991465-filtering-uis-are

## Heroku Nav

## Role: Design
## Co-conspirators: Matt Trifiro

The ideal Heroku nav should be consistent in appearance and behavior across properties, but also able to adapt according to context. As information such as user, app, addon, and org are made available, the nav should respond accordningly.

[Many](https://github.com/heroku/heroku-nav)
[ruby-based](https://github.com/heroku/fuji)
[attempts](https://github.com/heroku/fuji-sherpa) have been made to unify
this, but language specifity and general inflexibility have hindered their adoption
and maintenance.

[Boomerang](https://github.com/heroku/boomerang) is the latest incarnation of the Heroku nav.
Initially designed for use on add-on SSO pages, it can easily be re-purposed to function pan-Heroku.
It stands apart from its predecessors in that
it's rendered client-side by a Javascript widget. The most obvious benefits to this approach are
ease of integration and portability across sites regardless of their server-side lanuage.

## Iconography and Typography Pipelines

