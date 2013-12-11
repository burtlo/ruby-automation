# Day 2 - Files and Services

We want to build on the tools that we created yesterday, extending them to
talk to various file formats and start to use different sources and services for them.

## Parsing YAML files

A common format to store data is in YAML. Let's store some configuration for
where certain files of certain types should be stored.

* Format and Structure of YAML
* require 'yaml'
* File loading raw contents and parsing it with YAML::Load

## Parsing and Outputing JSON data

We want to parse some data that we have received and output some of that data
to the screen. Let's add a rake task that will show us all the names of the
Pokemon and their type information.

* Requiring JSON
* File loading raw contents and parsing it with JSON
* Talk about alternative JSON implementations

## Parsing and Outputing CSV data

* Various CSV methods
* Reminder that CSV rewind is required

## Parsing XML with Nokogiri

* Loading and Parsing XML
* finding children
* A quick introduction to XPATH

## Sinatra

Using Sinatra we can create simple interfaces that allow us to mock up existing
services. So we will solve the same problem we just solved but solve it again
through API endpoints

* Installing the Gem
* require 'sinatra'
* Sinatra DSL: get '/path' do ; "response" ; end
* Running and viewing the server `ruby server.rb`
* Setting up support for new paths for our data examples

## Faraday and HTTParty

Using Sinatra we can create simple interfaces that allow us to mock up existing
services. So we will solve the same problem we just solved but solve it again
through API endpoints

* Creating a connection
* Querying a particular URL
* Reading the repsonse from the body

## Structs and OpenStructs

The data that we have received can get really messy. We want to explore various
ways that we can structure that data to make it easier for us to manage.

* Struct limitations and benefits (speed)
* OStruct - require 'ostruct', flexibility, and performance impact

# Custom Classes

The data that we have received can get really messy. We want to explore various
ways that we can structure that data to make it easier for us to manage.

* Classes - initialize, named parameters, attr_reader, attr_writer, attr_accessor

# Thor: Creating our Own Command Line tool

With the remaining time in the day we will create our own command-line client
tool (when Rake just won't do). That allows us to specify our own custom
commands and arguments.

* Thor

### Resources

* http://www.awesomecommandlineapps.com/gems.html
* http://www.yaml.org/YAML_for_ruby.html
* http://pro.jsonlint.com/
* http://rubydoc.info/stdlib/csv/frames
* http://nokogiri.org/
* http://www.sinatrarb.com/
* https://github.com/lostisland/faraday
* https://github.com/jnunemaker/httparty
* http://rubydoc.info/stdlib/core/Struct
* http://rubydoc.info/stdlib/ostruct/frames
* https://github.com/erikhuda/thor