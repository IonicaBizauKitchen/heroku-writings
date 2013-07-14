Today we’re happy to announce Heroku’s Europe region, available in public beta. With more than [3 million apps](https://www.heroku.com/) running on our platform from developers all over the globe, it's not surprising that we've had high demand for Heroku in more regions of the world. After collaborating closely with customers during private beta, we're now ready to offer Heroku services in Europe to all customers as part of a public beta. The Europe region runs Heroku applications from datacenters located in Europe, offering improved performance for users in that region.

## One Heroku, Two Continents

The Europe region offers all the features of the existing US region. Both regions run apps on infrastructure dedicated to each region, but are managed by the same unified Heroku interface you already know. This provides powerful global app management with isolated, geolocated infrastructure:

<img src="https://s3.amazonaws.com/f.cl.ly/items/0s3u2J2K0U2E1i3S062n/how_europe_works.svg" class="stretchy">

## Faster Apps

The physical proximity of the Europe region to European end-users means reduced latency, often resulting in a dramatic improvement in app responsiveness to those users. We’ve observed performance improvements of 100ms per request or more for European end-users:

<img src="https://s3.amazonaws.com/f.cl.ly/items/0D040q1E1d1y3z1w2Q22/eu_response_times.svg" alt="Lower Latency in Europe" class="stretchy">

## A Familiar Workflow

All Heroku users can now create and deploy apps to the Europe region:

    $ heroku create --region eu
    $ git push heroku master

Once the app is created, you can interact with it just like any other Heroku app.

## Easy App Migration with Heroku Fork

<p>To ease the process of migrating existing applications to the Europe region, we created <a href="https://devcenter.heroku.com/articles/app-migration#fork-application">heroku fork</a>, a new addition to the Heroku CLI. Heroku fork copies an app's Heroku Postgres data and config vars, and re-provisions all its add-ons. If you have an existing app you’d like to run in the Europe region, check that you’ve got the most recent <a href="https://devcenter.heroku.com/articles/heroku-command#installing-the-heroku-cli">Heroku toolbelt</a> installed and use Heroku fork to create a running copy of your app in the new region:</p>

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
  <li>
    <a href="https://addons.heroku.com/heroku-postgresql">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/46/original.png">
      <span>Heroku Postgres</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/mongolab">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/750/original.png">
      <span>MongoLab</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/memcachier">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/322/original.png">
      <span>Memcachier</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/openredis">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/632/original.png">
      <span>openredis</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/newrelic">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/144/original.png">
      <span>New Relic</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/websolr">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/26/original.png">
      <span>Websolr</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/scheduler">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/176/original.png">
      <span>Scheduler</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/deployhooks">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/21/original.png">
      <span>Deploy Hooks</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/sendgrid">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/58/original.png">
      <span>SendGrid</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/airbrake">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/406/original.png">
      <span>Airbrake</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/papertrail">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/360/original.png">
      <span>Papertrail</span>
    </a>
  </li>
  <li>
    <a href="https://addons.heroku.com/cleardb">
      <img src="https://s3.amazonaws.com/assets.heroku.com/addons.heroku.com/catalogs/303/original.png">
      <span>ClearDB</span>
    </a>
  </li>
</ol>

To discover which add-ons are available in the Europe region, [search for 'europe' on the addons homepage](https://addons.heroku.com/?q=europe) or use the new `--region` flag in the heroku CLI:

    $ heroku update
    $ heroku addons:list --region eu

## Customer Success

Several Heroku customers have already deployed their production Heroku apps to the Europe region for improved performance. For example, top Swedish television network TV4 is currently running its video on demand service [TV4 Play](http://www.tv4play.se/) out of Heroku’s Europe region. TV4 CTO Per Åström says:

> Deploying our app closer to our users in Heroku's Europe region gave us a 150ms improvement in web performance. Based on this win for our users, we’re moving all of our apps to the Europe region.

Digital agencies and other customers delivering user-facing mobile and social apps have also benefited from improved performance in the Europe region. For example, app development company [Betapond](http://betapond.com/) COO Conor Ryan says:

> Deploying our Facebook apps live to the Heroku cloud in the EU was pain-free and as easy as staging. We're delighted to see an average of 11% improvement in page load times since making the switch. Consumers don't tolerate waiting, particularly on mobile devices, so Heroku's EU contribution to a snappy user experience is a big boost for Betapond and our customers.

## Safe Harbor Compliance is Coming Soon

Heroku is not yet a registered participant in the Safe Harbor program. We’ve laid the groundwork for becoming Safe Harbor certified and expect to have it soon. The Europe region public beta is designed to let you build high-performance apps for European users. It does not currently address data residency or jurisdiction concerns. You should assume that some portions of your app and its data will be in, or pass through,
datacenters located in the US.

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