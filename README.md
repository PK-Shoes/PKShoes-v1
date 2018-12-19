# PKShoes

## Overview
A webapp that helps traceur and freerunners choose what shoes best fit their needs for parkour and freerunning.

## Environment
* Ruby 2.5.3
* Rails 5.2.2
* PostgreSQL 11.1

## Setup

### Clone Repository

```
git clone https://github.com/PK-Shoes/PKShoes-v1.git
cd PKShoes-v1
bundle install
cp config/database.yml-dist config/database.yml
```

### Secrets
Secrets encrypted in `credentials.yml.enc`.

The master key is saved to the DevOps Manfiest Google doc. Copy and paste the key to the `config/` 
folder in a file called `master.key`. This key is required for running the server locally, 
setting up the database, and running tests.

To edit secrets:
```
EDITOR=vim rails credentials:edit
```

### Database Setup
```
bundle exec rails db:setup
```

## Development

### Run Tests

To run tests (along with rubocop and brakeman), run the following:

```
bundle exec rake test
```

To run System/Capybara Tests, run the following:

```
rails test:system
```

### Code Analysis

[Brakeman](https://github.com/presidentbeef/brakeman) is used for security analysis 
and [Rubocop](https://github.com/bbatsov/rubocop) is used for style analysis.

Both of these should already run automatically whenever the regular tests are run, but if you want to
run them individually, the commands for them are run below.

```
bundle exec brakeman
bundle exec rubocop
```

### Local Server

To start the local server, run:

```
rails s
```

You should be able to access your site locally on http://localhost:3000/