tags:
- Ruby on Rails
- Postgres
- HOWTO
date: 2019-07-09 17:20:04.249812361 +00:00

---


# Making Postgres work with Rails

_Every single time I try to set up Postgres with a new project, I run into some issues. This short HOWTO is mostly for me to remember how to make it work._

## Installation

```
apt get install postgresql libpq-dev
gem install pg
```

## Creating a new user

If you want to check your `config/database.yml` into the repozitory, you should keep `username` and `password` out of it.

And you can: just create a new user *with the same name as your system user*.

```
sudo -u postgres createuser -s $(whoami)
```

## Fixing authentication errors

Open `/etc/postgresql/10/main/pg_hba.conf` and look for this line:

```
local   all             all                                     peer
```

Now change `peer` authentication method to `trust`.

```
service postgresql restart
```

## Fixing permission errors

```
sudo -u postgres psql -U postgres
```

```sql
#GRANT CONNECT ON DATABASE postgres TO root;
ALTER USER myuser WITH SUPERUSER;
```

## Bootstrapping the databases

And that's it! Now just run the usual `bundle exec rails db:create db:migrate` and you should be good to go.
