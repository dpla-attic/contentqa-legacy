Contentqa
===

This is the legacy content QA Rails engine for the [DPLA Platform](https://github.com/dpla/platform).


Installation
---

The Content-QA sub-application uses [Delayed Job](https://github.com/collectiveidea/delayed_job), and asynchronous priority queue system.  When installing, add the Gem to your gemfile run the following commands to generate delayed job and create a table in the database:

```
rails generate delayed_job
rails generate delayed_job:active_record
rake db:migrate
```

To start `delayed_job` in a development environment, use:

```
$ rake jobs:work
```

When you start the Content-QA sub-application, you also need to start the delayed job daemon:

```
RAILS_ENV=[ENVIRONMENT] script/delayed_job start
# Example: 
RAILS_ENV=production script/delayed_job start
```

When you stop the Content-QA sub-appliction, stop the delayed job daemon:

```
RAILS_ENV=[ENVIRONMENT] script/delayed_job stop
# Example:
RAILS_ENV=production script/delayed_job stop
```

License
--------
This application is released under a AGPLv3 license.

Copyright Digital Public Library of America, 2013-2016