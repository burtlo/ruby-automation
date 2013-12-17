!SLIDE title

# Parsing XML
The data structure we all love to hate

!SLIDE title

XML stands for eXtensible Markup Language. XML is designed to transport and store data. XML is important to know, and very easy to learn.

!SLIDE title

## Example XML

```
<person>
  <name>franklin</name>
  <age>36</age>
  <city>Denver</city>
</person>
```

!SLIDE title

## More XML

```
<person>
  <name>franklin</name>
  <favorite_color>blue</favorite_color>
  <favorite_rake_task>db:test:prepare</favorite_rake_task>
</person>
```

!SLIDE title

## A Little More XML

```
<person>
  <name>franklin</name>
  <favorites>
    <color>blue</color>
    <rakeTask>db:test:prepare</rakeTask>
  </favorites>
</person>
```

!SLIDE title

## Last Bit of XML

```
<person>
  <name>franklin</name>
  <placesLived>
    <place>Los Angeles, CA</place>
    <place>Denver, CO</place>
    <place>Washington D.C.</place>
  </placesLived>
</person>
```

!SLIDE title

## Parsing XML Files

!SLIDE title

## Require XML

```ruby
require 'rexml'
```

!SLIDE title

## Nokogiri

REXML is generally considered too slow. So there is a gem that is often installed to do that.

!SLIDE title commandline

## Install Nokogiri

```
$ gem install nokogiri
```

!SLIDE title

## Require Nokogiri

```ruby
require 'nokogiri'
```

!SLIDE title

## Load the File

```ruby
require 'nokogiri'

file_contents = File.read(filename)
```

!SLIDE title

## Parse the Contents

```ruby
require 'nokogiri'

file_contents = File.read(filename)

data = Nokogiri::XML(file_contents)
```

!SLIDE title

## What Does the Data Look Like?

```
<person>
  <name>franklin</name>
  <age>36</age>
  <city>Denver</city>
</person>
```

```ruby
puts data.xpath("person/name").text
puts data.xpath("person/age").text
puts data.xpath("person/city").text
```

!SLIDE title

## What Does the Data Look Like?

```
<person>
  <name>franklin</name>
  <favorites>
    <color>blue</color>
    <rakeTask>db:test:prepare</rakeTask>
  </favorites>
</person>
```

```ruby
puts data.xpath("person/name").text
puts data.xpath("person/favorites/color").text
puts data.xpath("person/favorites/rakeTask").text
```

!SLIDE title

## What Does the Data Look Like?

```
<person>
  <name>franklin</name>
  <placesLived>
    <place>Los Angeles, CA</place>
    <place>Denver, CO</place>
    <place>Washington D.C.</place>
  </placesLived>
</person>
```

```ruby
puts data.xpath("person/name").text
puts data.xpath("person/placesLived/place")[0].text
puts data.xpath("person/placesLived/place")[1].text
puts data.xpath("person/placesLived/place")[2].text
```

!SLIDE title

# Goal

!SLIDE commandline

# Parse XML File

```
$ rake dev:database:xml:info
dev_user connects a mysql2 database named pokemon-dev
$ rake test:database:xml:info
test_user connects a mysql2 database named pokemon-test
$ rake prod:database:xml:info
root connects a mysql2 database named pokemon
```

!SLIDE title

## Review and Questions