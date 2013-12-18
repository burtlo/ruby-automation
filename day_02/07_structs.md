!SLIDE title

# Structuring Data
Structs and OpenStructs

!SLIDE title

Hashes and Arrays are **fine for relatively small
data**, but when the data gets **much more
complicated** the **need to structure arises**. It also
just makes things more convienent.

!SLIDE title

## Point in a 2D System

## [ x, y ]

!SLIDE title

## Not Very Descriptive Names

```ruby
origin = [ 0, 0 ]
puts origin.first
puts origin.last
```

!SLIDE title

## Dream Driven Development

```ruby
origin = Point.new(0,0)
puts origin.x
puts origin.y
```

!SLIDE title

## Struct

A Struct is a **convenient way** to **bundle a
number of attributes together**, using accessor
methods, **without having to write an explicit class.**

!SLIDE title

## Point as a Struct

```ruby
Point = Struct.new(:x,:y)
```

!SLIDE title

## Using Our Point

```ruby
Point = Struct.new(:x,:y)
origin = Point.new(0,0)
puts origin.x
puts origin.y
```

# Goal

!SLIDE

## Structure the Database Data With a Struct

```ruby
dev_db = Database.new(...)
puts dev_db.adapter
puts dev_db.database
puts dev_db.user
puts dev_db.password
```

```
$ rspec spec/structs_spec.rb
....

Finished in 0.00115 seconds
4 example, 0 failures
```

!SLIDE title

## Review and Questions