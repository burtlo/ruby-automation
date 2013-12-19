!SLIDE title

# Parsing JSON

!SLIDE title

JSON (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.

!SLIDE title

## Example JSON

```
{ "name": "franklin",
  "age": 36,
  "city": "Denver" }
```

!SLIDE title

## More JSON

```
{ "name": "franklin",
  "favorite_color": "blue",
  "favorite_rake_task": "db:test:prepare" }
```

!SLIDE title

## A Little More JSON

```
{ "name": "franklin",
  "favorites":
  {
    "rake_task": "db:test:prepare",
    "color": "blue"
  }
}
```

!SLIDE title

## Last Bit of JSON

```
{ "name": "franklin",
  "places_lived":
  [
    "Los Angeles, CA",
    "Denver, CO",
    "Washington D.C."
  ]
}
```

!SLIDE title

## Parsing JSON Files

!SLIDE title

## Require JSON

```ruby
require 'json'
```

!SLIDE title

## Load the File

```ruby
require 'json'

file_contents = File.read(filename)
```

!SLIDE title

## Parse the Contents

```
require 'json'

file_contents = File.read(filename)

data = JSON.parse(file_contents)
```

!SLIDE title

## What Does the Data Look Like?

```
{ "name": "franklin",
  "age": 36,
  "city": Denver }
```

```ruby
puts data["name"]
puts data["age"]
puts data["city"]
```

!SLIDE title

## What Does the Data Look Like?

```
{ "name": "franklin"
  "favorites":
  {
    "rake_task": "db:test:prepare"
    "color": "blue"
  }
}
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
{ "name": "franklin"
  "places_lived":
  [
    "Los Angeles, CA",
    "Denver, CO",
    "Washington D.C."
  ]
}
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

# Parse JSON File

```
$ rspec spec/parsing_json_spec.rb
............

Finished in 0.00115 seconds
12 example, 0 failures
```

!SLIDE title

## Review and Questions