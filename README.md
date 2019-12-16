# Bouncer Stack

A pgbouncer postgres stack using docker/docker-compose purely for
entertainment purposes.

### Notes

- Postgres requires a initial user/password to be set via env vars
- Pgbouncer needs to know what postgres to talk to, and what user/password
  to use for authenticating, which can also be set via env vars
- I'm using docker-compose x-common-variables (aka yaml anchors) to set the
  user/password once

### Running

- To bring the stack up just run `docker-compose up`
- Once the stack is up, postgres will be accessible via pgbouncer connection
  pooling at localhost:6432
- Then, you can use the psql client to connect to postgres via pgbouncer,
  e.g. `psql -h localhost -p 6432 -d postgres -U admin`
- Once you're done, you can stop, and bring down the stack with
  `docker-compose down`
