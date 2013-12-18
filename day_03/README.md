# Day 3 - Databases and Data Structures

Now that we're starting feeling comfortable with Ruby and various tools, let's
start to focus on testing with RSpec. We will also expand our tools to talk to
multiple databases.

## RSpec Beliefs and Introduction

* Behavior Driven Design
* Syntax: describe, context, it
* Syntax: before, before all, after, after all
* Expectation Syntax (old and new)
* Running test

## Writing specifications for our custom model objects

* Implementation using syntax and expectation syntax

## Drying up the tests

* Implicit Subject
* let
* its (though going away)
* shared examples

## RSpec Options

* Running tests with different flags
* Rpsec additional options (color and output formats)
* Running Guard RSpec

## ActiveRecord - 1

ORM and how they can help you make your life a whole lot easier (and sometimes
harder).

* Installing and Requiring Gem
* Configuring with Database Information (sqlite3)
* Modeling an existing database table that conforms to standards
* Querying for data: find, all, where, order, limit

## ActiveRecord - 2

* Modeling an existing database table that does not conform to standards
* setting table name
* setting primary key
* setting up composite key

## Rspec - Fixtures and Stubs

* Setting up manageable fixture files and database
* Alternative to fixtures using stubs

## Rspec - Mocks

* Setting up an expectation on calls

### Resources

* https://www.relishapp.com/rspec/
* http://tutorials.jumpstartlab.com/topics/internal_testing/rspec_practices.html
* http://guides.rubyonrails.org/active_record_basics.html
* http://guides.rubyonrails.org/migrations.html
* http://guides.rubyonrails.org/active_record_validations.html
* http://guides.rubyonrails.org/active_record_callbacks.html
* http://guides.rubyonrails.org/association_basics.html
* http://guides.rubyonrails.org/active_record_querying.html
* https://github.com/composite-primary-keys/composite_primary_keys
