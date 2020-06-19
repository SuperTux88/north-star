# Production setup

TODO: This should be clearer.

## Setup

1. Make sure Ruby 2.6 or newer **and Redis** is installed on the server
2. Clone the repository
3. `cp data/config.yml.example data/config.yml`
4. `cd _server`
5. `gem install bundler`
6. `bin/bundle install --full-index`
7. `bin/rake assets:precompile`
8. `bin/puma -e production`

Note: north-star will try to connect to redis on `redis://localhost:6379/11` per default, which can be changed using the `REDIS_URL` environment variable.

## Nginx setup

`_docs/configs/nginx-example.com` holds an example of the production nginx configuration. This needs to be extended for SSL, asset compression, etc, but gives a starting point for mapping the subdomains.
