!SLIDE title

# Parsing YAML
What the Hell is YAML?

!SLIDE title

YAML is a **human friendly** data serialization standard for all programming languages. It is **white space** sensitive.

!SLIDE title

## Example YAML

```
name: franklin
age: 36
city: Denver
```

!SLIDE title

## More YAML

```
name: franklin
favorite_color: blue
favorite_rake_task: "db:test:prepare"
```

!SLIDE title

## A Little More YAML

```
name: franklin
favorites:
  rake_task: "db:test:prepare"
  color: blue
```

!SLIDE title

## Last Bit of YAML

```
name: franklin
places_lived:
  - Los Angeles, CA
  - Denver, CO
  - Washington D.C.
```

!SLIDE title

## Parsing YAML Files

!SLIDE title

## Require YAML

```ruby
require 'yaml'
```

!SLIDE title

## Load the File

```ruby
require 'yaml'

file_contents = File.read(filename)
```

!SLIDE title

## Parse the Contents

```
require 'yaml'

file_contents = File.read(filename)

data = YAML.load(file_contents)
```

!SLIDE title

## What Does the Data Look Like?

```
name: franklin
age: 36
city: Denver
```

```ruby
puts data["name"]
puts data["age"]
puts data["city"]
```

!SLIDE title

## What Does the Data Look Like?

```
name: franklin
favorites:
  rake_task: "db:test:prepare"
  color: blue
```

```ruby
puts data["name"]
puts data["favorites"]
puts data["favorites"]["rake_task"]
puts data["favorites"]["color"]
```

!SLIDE title

## What Does the Data Look Like?

```
name: franklin
places_lived:
  - Los Angeles, CA
  - Denver, CO
  - Washington D.C.
```

```ruby
puts data["name"]
puts data["places_lived"]
puts data["places_lived"][0]
puts data["places_lived"][1]
puts data["places_lived"][2]
```

!SLIDE title

# Goal

!SLIDE commandline

# Parse YAML File

```
$ rake dev:database:yml:info
dev_user connects a mysql2 database named pokemon-dev
$ rake test:database:yml:info
test_user connects a mysql2 database named pokemon-test
$ rake prod:database:yml:info
root connects a mysql2 database named pokemon
```

!SLIDE title

## Review and Questions