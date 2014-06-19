## Capturing the collective wisdom of the Node community

package.json files are magical things. They tell us everything we need to know about an app or package: what it's for, how to use it, what its dependencies are, and so on. The npm registry and website provide useful information about these packages and their relationships to one another, but little is publicly known about how people are actually piecing them together to build web apps. As a platform upon which thousands of Node apps are deployed every day, Heroku is in a unique position to gather data about common practices and share it with the Javascript community.

nomnom is an insomnolent and insatiable webservice that thrives on a steady diet of package.json files. Every time a Node app is deployed to Heroku, its package.json data is anonymized and fed to this service. In my talk I'll share some of the discoveries we've made by analyzing nomnom's data, like what dependencies are most widely used, how people are testing their apps, how much traction coffeescript and ES6 are getting, and how teams are handling private dependencies.

## Drafts

nomnom is an insomnolent and insatiable webservice that eats package.json files for a living. Every time a Node app is deployed to Heroku, its package.json data is anonymized and fed to this voracious service. nomnom has ingested well over a million packages to date, and shows no sign of slowing.

package.json files are magical things. They tell us everything we want to know about Node apps and npm packages, like what they're for, how they run, what packages they depend on, and more. The npm public registry and website tell us a great deal about the relationships between _packages_, but little is known about what dependencies people are actually using in their _apps_. Thanks to nomnom, we're starting to gain insight into npm trends at the app level. In my talk I'll share some of the fascinating discoveries I've made by analyzing nomnom's data:

- What dependencies are most common?
- How are people testing their apps?
- How much traction are Coffeescript and ES6 getting?
- What versions of Node are in vogue?
- How are people hosting private dependencies?

nomnom is an insatiable webservice that eats package.json files for a living. Every time a Node app is deployed to Heroku, its package.json data is anonymized and fed to this voracious service. nomnom has ingested well over a million packages to date, and shows no sign of slowing.

package.json files are magical things. Every node project has one, and it's the first place to look for everything you need to know about an app or package: what it's for, how to use it, and what packages it depends on. The npm registry and website give us useful data about the relationships between _packages_, but little is publicly known about what dependencies people are actually using in their _apps_. To shed some light on this, Heroku created nomnom, an insomnolent and insatiable webservice that thrives on a steady diet of package.json files. Every time a Node app is deployed to Heroku, its package.json data is anonymized and fed to this service, giving us insight into the development practices of the Node populous. In my talk I'll share some of the discoveries we've made by analyzing nomnom's data, like what dependencies are most widely used, how people are testing their web apps, how much traction coffeescript and ES6 are getting, and how teams are handling private dependencies.

Each package.json is a snowflake, and their aggregate is a blizzard of data.

The story of a million packages
Homage to package.json
The package.json diet.


Capturing the collective wisdom of the Node community

package.json files are magical things. They tell us everything we need to know about an app or package: what it's for, how to use it, what its dependencies are, and so on. The npm registry and website provide useful information about these packages and their relationships to one another, but little is publicly known about how people are actually piecing them together to build web apps. As a platform upon which thousands of Node apps are deployed every day, Heroku is in a unique position to gather data about common practices and share it with the Javascript community.

nomnom is an insomnolent and insatiable webservice that thrives on a steady diet of package.json files. Every time a Node app is deployed to Heroku, its package.json data is anonymized and fed to this service. In my talk I'll share some of the discoveries we've made by analyzing nomnom's data, like what dependencies are most widely used, how people are testing their apps, how much traction coffeescript and ES6 are getting, and how teams are handling private dependencies.
