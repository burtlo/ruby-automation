!SLIDE title

# Parsing CSV

!SLIDE title

A comma-separated values (CSV) (also sometimes called character-separated values, because the separator character does not have to be a comma) file stores tabular data (numbers and text) in plain-text form.

!SLIDE title

## Example CSV

```
name,age,city
franklin,36,Denver
```

!SLIDE title

## More CSV

```
name,favorite_color,favorite_rake_task
franklin,blue,db:test:prepare
```

!SLIDE title

## A Little More CSV

```
name,favorite_rake_task,favorite_rake_task
franklin,db:test:prepare,blue
```

!SLIDE title

## Last Bit of CSV

```
id,name
1,franklin
```

```
id,person_id,location
1,1,"Los Angeles, CA"
2,1,"Denver, CO"
3,1,"Washington D.C."
```

!SLIDE title

## Parsing CSV Files

!SLIDE title

## Require CSV

```ruby
require 'csv'
```

!SLIDE title

## Parse the File

```ruby
require 'csv'

data = CSV.read(filename)
```

!SLIDE title

## What Does the Data Look Like?

```
name,age,city
franklin,36,Denver
```

```ruby
puts data
# [["name", "age", "city"], ["franklin", "36", "Denver"]]
puts data[1][0]
puts data[1][1]
puts data[1][2]
```

!SLIDE title

## Another Way to Parse the Data

```ruby
data = CSV.read("name.csv",:headers => true)
puts data
# #<CSV::Table mode:col_or_row row_count:2>
puts data[0]['name']
puts data[1]['age']
puts data[1]['city']
```

!SLIDE title

# Goal

!SLIDE title

# Lets Not Parse CSV

!SLIDE title

## Review and Questions