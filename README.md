# Service Skeleton

Base structure for building API services

## Components

- Sinatra
- JSON
- Foreman
- Thin
- Dotenv
- Rspec

Extras:

- Active Record 4
- Postgres Adapter
- Sentry

## Getting Started

Clone repository and install dependencies:

```
git clone https://github.com/doejo/service-skeleton.git myapp
cd myapp
bundle install
```

Copy sample configuration files:

```
cp .env.sample .env
cp config/database.yml.sample config/database.yml
```

Create and migrate database:

```
rake db:create db:migrate
```

Start development server:

```
foreman start
```

By default, the service will be available at `http://localhost:5000`

## Rake tasks

```
rake console                # Start application console
rake db:create              # Creates the database from DATABASE_URL or config/database.yml for the current RAILS_ENV (use db:create:all to create all databases in the config)
rake db:create_migration    # Create a migration (parameters: NAME, VERSION)
rake db:drop                # Drops the database from DATABASE_URL or config/database.yml for the current RAILS_ENV (use db:drop:all to drop all databases in the config)
rake db:fixtures:load       # Load fixtures into the current environment's database
rake db:migrate             # Migrate the database (options: VERSION=x, VERBOSE=false, SCOPE=blog)
rake db:migrate:status      # Display status of migrations
rake db:rollback            # Rolls the schema back to the previous version (specify steps w/ STEP=n)
rake db:schema:cache:clear  # Clear a db/schema_cache.dump file
rake db:schema:cache:dump   # Create a db/schema_cache.dump file
rake db:schema:dump         # Create a db/schema.rb file that is portable against any DB supported by AR
rake db:schema:load         # Load a schema.rb file into the database
rake db:seed                # Load the seed data from db/seeds.rb
rake db:setup               # Create the database, load the schema, and initialize with the seed data (use db:reset to also drop the database first)
rake db:structure:dump      # Dump the database structure to db/structure.sql
rake db:version             # Retrieves the current schema version number
rake raven:test[dsn]        # Send a test event to the remote Sentry server
rake test                   # Run RSpec code examples
```

## Testing

Prepare test database first:

```
rake db:schema:load RACK_ENV=test
```

Execute test suite:

```
rake test
```

## License

The MIT License (MIT)

Copyright (c) 2014 Doejo LLC