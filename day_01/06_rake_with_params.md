!SLIDE title

# Rake With Parameters

!SLIDE title

Often times our tools need to take inputs that allow us to do a similar
operation with different parameters. Lets look at providing inputs to our
rake tasks.

!SLIDE title

## Static Introduction

```ruby
task "introduction" => [ "greetings:formal" ] do
  puts "Hi My Name is Frank"
  Rake::Task['goodbye'].invoke
end
```

```
$ rake introduction
hello
Hi My Name is Frank
goodbye
```

!SLIDE title

## A Dynamic Introduction

```ruby
task "introduction" => [ "greetings:formal" ] do
  puts "Hi My Name is YOURNAMEHERE"
  Rake::Task['goodbye'].invoke
end
```

!SLIDE title

## Task Parameters Format

```ruby
task "TASKNAME", [ "PARAM1", ... ] => [ "DEPENDENT_TASK1", ... ] do |task,params|
  # ... task related code ...
end
```

!SLIDE title

## An Example

```ruby
task "introduction", [ "name" ] => [ "greetings:formal" ] do |task,params|
  puts params.name
  # ... task related code ...
end
```

!SLIDE title

## How do I get `params.name` into my string?

!SLIDE title

## String Interpolation

It allows us to escape the string briefly to insert most any Ruby code we want
to insert into the string.

!SLIDE title

## Example of Interpolating Strings

```ruby
puts "1 + 1 = #{1 + 1}"
name = "Jorge"
puts "My Name Is #{name}"
```

!SLIDE title

## Our Task Parameters String Interpolated

```ruby
task "introduction", [ "name" ] => [ "greetings:formal" ] do |task,params|
  puts "Hi My Name is #{params.name}"
  Rake::Task['goodbye'].invoke
end
```

!SLIDE title commandline

## How Do I Use This Parameter?

```
$ rake task[PARAM1,...]
```

!SLIDE title commandline

## Example Usage

```
$ rake introduction[Bilbo]
hello
Hi My Name is Bilbo
goodbye
```

!SLIDE title

# Goal

!SLIDE title commandline

# Add Rake Parameters

```
$ rake downloads:copy[images]
$ rake downloads:copy[txt]
$ rake downloads:copy[videos]
```

!SLIDE title

## Review and Questions
