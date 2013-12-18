!SLIDE title

# Sinatra
Setting up your own web server

!SLIDE title

Sinatra is a DSL for quickly creating web applications in Ruby with minimal effort

!SLIDE title commandline

## Install the Gem

```
$ gem install sinatra
```

!SLIDE title

## Create Server File

```
$ touch server.rb
```

!SLIDE title

## Sinatra DSL

```ruby
require 'sinatra'

get '/' do
  'Hello World!'
end
```

!SLIDE title commandline

```
$ ruby server.rb
== Sinatra/1.4.2 has taken the stage on 4567 for development with backup from Thin
>> Thin web server (v1.5.1 codename Straight Razor)
>> Maximum connections set to 1024
>> Listening on localhost:4567, CTRL+C to stop
```

!SLIDE title

## http://localhost:4567
View the Website in Your Browser

!SLIDE title

## Creating a Sample API

```ruby
require 'sinatra'

get '/databases.json' do
  File.read("database.json")
end

# ...
```

!SLIDE title

## Restart the Server After Changes

!SLIDE title

# Goal

!SLIDE title

## Setup two API Endpoints with Data

* http://localhost:4567/databases.json
* http://localhost:4567/databases.xml

!SLIDE title

## Review and Questions