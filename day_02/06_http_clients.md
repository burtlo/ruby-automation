!SLIDE title

# HTTP Clients
Talking with (our) server

!SLIDE title

Ruby comes with a **net** library that provides HTTP, FTP, IMAP, POP3 and SMTP. **But most Ruby developers prefer to use other libraries**

!SLIDE title

## Faraday or HTTParty

!SLIDE title commandline

## Install the Gem

```
$ gem install Faraday
```

!SLIDE title

## Create Client File

```
$ touch client.rb
```

!SLIDE title

## Requiring Faraday

```ruby
require 'faraday'
```

!SLIDE title

## Creating a Connection

```ruby
require 'faraday'

connection = Faraday.new(:url => "http://localhost:4567")
```

!SLIDE title

## Using the Connection

```ruby
require 'faraday'

connection = Faraday.new(:url => "http://localhost:4567")

response = connection.get("database.json")
```

!SLIDE title

## Parsing the Response

```ruby
require 'faraday'

connection = Faraday.new(:url => "http://localhost:4567")

response = connection.get("database.json")

raw_data = response.body
```

!SLIDE title

## It's All the Same After That

!SLIDE title

## JSON

```
require 'faraday'
require 'json'

connection = Faraday.new(:url => "http://localhost:4567")
response = connection.get("database.json")
raw_data = response.body

data = JSON.parse(raw_data)
puts data
```

!SLIDE title

## XML

```
require 'faraday'
require 'nokogiri'

connection = Faraday.new(:url => "http://localhost:4567")
response = connection.get("database.json")
raw_data = response.body

data = Nokogiri::XML(raw_data)
puts data
```

!SLIDE title

# Goal

!SLIDE title commandline

## Consume Your Server API

* http://localhost:4567/databases.json
* http://localhost:4567/databases.xml

```
$ rspec spec/http_spec.rb
....

Finished in 0.00115 seconds
4 example, 0 failures
```

!SLIDE title

## Review and Questions