Today we’re happy to announce Heroku’s Europe region, available in public beta. With more than [3 million apps](https://www.heroku.com/) running on our platfrom from developers all over the globe, it's not surprising that we've had high demand for Heroku in more regions of the world. After collaborating closely with customers during private beta, we're now ready to offer Heroku services in Europe to all customers as part of a public beta. The Europe region runs Heroku applications from datacenters located in Europe, offering improved performance for users in that region.

## One Heroku, Two Continents

The Europe region offers all the features of the existing US region. Both regions run apps on infrastructure dedicated to each region, but are managed by the same unified Heroku interface you already know. This provides powerful global app management with isolated, geolocated infrastructure:

<img src="https://s3.amazonaws.com/f.cl.ly/items/0s3u2J2K0U2E1i3S062n/how_europe_works.svg" class="stretchy">

## Faster Apps

If your customers are outside the US, deploying your apps to Heroku’s Europe region can improve app performance for your end-users. With this beta release, apps running in Europe avoid significant routing delays that EU users would otherwise encounter when accessing apps in US data centers. For customer-facing web and mobile apps, this performance difference often means a dramatic improvement in app responsiveness. We’ve observed performance improvements of 100ms per request or more for European end-users:

<img src="https://s3.amazonaws.com/f.cl.ly/items/3k181A0r1m2Z1j1i0o3L/eu_latency.svg#.png" alt="Lower Latency in Europe" class="stretchy">

## A Familiar Workflow

All Heroku users can now create and deploy apps to the Europe region:

    $ heroku create --region eu
    $ git push heroku master

## Easy App Migration with Heroku Fork

<p>To ease the process of migrating existing applications to the Europe region, we created <a href="https://devcenter.heroku.com/articles/app-migration#fork-application">heroku fork</a> , a new addition to the Heroku CLI. Heroku fork copies an app's Heroku Postgres data and config vars, and re-provisions all its add-ons. If you have an existing app you’d like to run in the Europe region, check that you’ve got the most recent<a href="https://devcenter.heroku.com/articles/heroku-command#installing-the-heroku-cli">Heroku toolbelt</a> installed and use Heroku fork to create a running copy of your app in the new region:</p>

    $ heroku fork --region eu
    Creating fork myapp-332... done
    Copying slug... done
    Adding newrelic:professional... done
    Copying config vars... done
    Fork complete, view it at http://myapp-332.herokuapp.com/

Note: `heroku fork` will not move any domains or scale your app past a single dyno, so you're free to decide when your app will be made available to your customers. For more information about this powerful new feature, see the <a href="https://devcenter.heroku.com/articles/app-migration#fork-application">Dev Center article on heroku fork</a>.

## Add-ons

[More than 60 add-ons](https://addons.heroku.com/?q=europe) are currently available in the Europe region, with more on the way. To ensure that your app has fast access to its data wherever it’s deployed, Heroku automatically provisions latency-sensitive add-ons in your app’s region. Many add-ons are already available to apps in the Europe region, including:

<ol class="addon_matrix">
  <li><a href="https://addons.heroku.com/heroku-postgresql" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/46/original.png')">Heroku Postgres</a></li>
  <li><a href="https://addons.heroku.com/mongolab" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/750/original.png')">MongoLab</a></li>
  <li><a href="https://addons.heroku.com/memcachier" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/322/original.png')">Memcachier</a></li>
  <!-- <li><a href="https://addons.heroku.com/rediscloud" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/740/original.png')">Redis Cloud</a></li> -->
  <li><a href="https://addons.heroku.com/openredis" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/632/original.png')">openredis</a></li>
  <li><a href="https://addons.heroku.com/newrelic" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/144/original.png')">New Relic</a></li>
  <li><a href="https://addons.heroku.com/websolr" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/26/original.png')">Websolr</a></li>
  <li><a href="https://addons.heroku.com/scheduler" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/176/original.png')">Scheduler</a></li>
  <li><a href="https://addons.heroku.com/deployhooks" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/21/original.png')">Deploy Hooks</a></li>
<li><a href="https://addons.heroku.com/sendgrid" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/58/original.png')">SendGrid</a></li>
<li><a href="https://addons.heroku.com/airbrake" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/406/original.png')">Airbrake</a></li>
<li><a href="https://addons.heroku.com/papertrail" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/360/original.png')">Papertrail</a></li>
<li><a href="https://addons.heroku.com/cleardb" style="background-image: url('https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/303/original.png')">ClearDB</a></li>
</ol>

## Customer Success

Several Heroku customers have already deployed their production Heroku apps to the Europe region for improved performance. For example, top Swedish television network TV4 is currently running its video on demand service [TV4 Play](http://www.tv4play.se/) out of Heroku’s Europe region. TV4 CTO Per Åström says:

> Deploying our app closer to our users in Heroku's Europe region gave us a 150ms improvement in web performance. Based on this win for our users, we’re moving all of our apps to the Europe region.

Digital agencies and other customers delivering user-facing mobile and social apps have also benefited from improved performance in the Europe region. For example, app development company [Betapond](http://betapond.com/) COO Conor Ryan says:

> Deploying our Facebook apps live to the Heroku cloud in the EU was pain-free and as easy as staging. We're delighted to see an average of 11% improvement in page load times since making the switch. Consumers don't tolerate waiting, particularly on mobile devices, so Heroku's EU contribution to a snappy user experience is a big boost for Betapond and our customers.

## Safe Harbor Compliance is Coming Soon

Heroku is not yet a registered participant in the Safe Harbor program. We’ve laid the groundwork for becoming Safe Harbor certified and expect to have it soon. The Europe region public beta is designed to let you build high-performance apps for European users. It does not currently address data residency or jurisdiction concerns. You should assume that some portions of your app and it's data will be in, or pass through,
data centers located in the US.

## We Want Your Feedback

<p>
  If you have comments or questions about the Heroku Europe region, email us at <a href="mailto:eu-beta@heroku.com" class="active">eu-beta@heroku.com</a>.
  To receive email updates about the Heroku Europe region as it progresses to general availability, subscribe to the beta mailing list below.
</p>

<form action="http://lists.heroku.com/t/r/s/jdputr/" class="call_to_action simple_signup" method="post">
<input class="email" id="jdputr-jdputr" name="cm-jdputr-jdputr" placeholder="Enter your heroku email address" type="text" required='required'>
<input class="submit" type="submit" value="Subscribe">
</form>

## Additional Resources

- [Screencast: Introducing Regions](https://vimeo.com/64197387)
- [Dev Center: Regions](https://devcenter.heroku.com/articles/regions)
- [Dev Center: Configure SSL for Europe Region Apps](https://devcenter.heroku.com/articles/regions#ssl)
- [Dev Center: Production Tier Postgres Database Migration](https://devcenter.heroku.com/articles/heroku-postgres-follower-databases)
- [Dev Center: Starter Tier Postgres Database Migration](https://devcenter.heroku.com/articles/upgrade-heroku-postgres-with-pgbackups)