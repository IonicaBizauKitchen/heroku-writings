http://en.wikipedia.org/wiki/Apdex
Instrumentation for memcached mongo mysql redis

## appdex score

it is a proxy for the user experience of your site. user frustration threshold: high for rails, low for node,

satisfied
tolerating
frustrating (bailed)

Sample appdex score: 0.97(/1) (like probablity: everybody happy at one. nobody happy at zero)

##

- [Real User Monitoring](http://en.wikipedia.org/wiki/Real_user_monitoring) provides a transaction trace through entire request (most useful with full browser trace)
- request parameter filtering: passwords, credit cards, etc
- forrest hangs out on the Settings > Environment page


## Target Audience

- MEAN stack + redis
- redis is slow enough on PAAS to want to see numbers
- PAAS
- A lot Ghost instances

##

- pagerduty integration
- availabilty monoitoring: provide a URL to ping
- per-url: track as key transaction
- key transaction policies:

all instrumentation depends on monkey patching http request headers: the new
relic model is transactional: request and response lifecycle. single-pages
apps don't have this.


abstract computronium hours

Newrelic supports cluster because it just kind of works.


harvest cycle is 60 seconds. max of 20 execptions. if they get close to 64k, they get gzipped


availability monitoring in five availability zones. multiple locations in US and Europe.