# What's Next for Zeke at Heroku?

Here's

## App Gallery

Together with the Partner team and [Eric Holmes](http://ejholmes.github.com/) from Luminosity Group, we're building a gallery of apps running on Heroku, and using the Heroku API to collect metadata about those apps, like what language they're built in, how many dynos they're running, and what addons they're using. The idea is that this app will eventually replace success.heroku.com, and will be a webservice that other Heroku properties can consume. Some examples:

- On addons.heroku.com, showcase apps using a particular addon or addon "recipe".
- On partners.heroku.com, display a portfolio of apps created by that agency.
- On dashboard.heroku.com, display apps as products/projects with individual identities.

## Node Buildpack

Heroku

https://dataclips.heroku.com/hlxqofowidhnoqievnjfsmsoryyp
David and I spent the last week dissecting the Node buildpack and going through the open github issues.

## Anvil Doesn't Exist

https://devcenter.heroku.com/articles?q=anvil

I heard three people at Waza say they don't use Heroku for their more specialized apps because they don't know how to deal with binary dependencies. Anvil is already here, but the lack of branding and promotion around it has kept it from entering the public consciousness.

The [current Devcenter advice for packaging binary dependencies](https://devcenter.heroku.com/articles/buildpack-binaries) is to use vulcan, and the Node Buildpack is using vulcan.

## Buildpack Directory

- Find out how this list has been maintained: https://devcenter.heroku.com/articles/third-party-buildpacks
- http://buildpacks.heroku.com/
- https://github.com/buildpacks

## Heroku CLI Plugin Directory

An auth-free first-come-first-serve revival of herocutter. In it's simplest form, a searchable list of github repos.

## The Directory Pattern

## Heroku Nav

[Fuji](https://github.com/heroku/fuji), [Sherpa](https://github.com/heroku/fuji-sherpa) and
especially [Boomerang](https://github.com/heroku/boomerang) are projects that have attempted

The ideal Heroku nav is visually and functionally consistent across properties, but able to adapt to its context. Contextual information might include user, app, addon, etc.

## Heroku Iconography and Typography Pipeline



