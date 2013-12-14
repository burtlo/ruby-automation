!SLIDE

# Rake With Parameters

!SLIDE

Often times our tools need to take inputs that allow us to do a similar
operation with different parameters. Lets look at providing inputs to our
rake tasks.

!SLIDE

# Static Introduction

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

!SLIDE

# A Dynamic Introduction

```ruby
task "introduction" => [ "greetings:formal" ] do
  puts "Hi My Name is YOURNAMEHERE"
  Rake::Task['goodbye'].invoke
end
```

!SLIDE

# Task Parameters Format

```ruby
task "TASKNAME", [ "PARAM1", "PARAM2", ... ] => [ "DEPENDENT_TASKNAME2", ... ] do |task,params|
  # ... task related code ...
end
```

!SLIDE

# An Example

```ruby
task "introduction", [ "name" ] => [ "greetings:formal" ] do |task,params|
  puts params.name
  # ... task related code ...
end
```

!SLIDE

# How do I get `params.name` into my string?

!SLIDE

# String Interpolation

It allows us to escape the string briefly to insert most any Ruby code we want
to insert into the string.

!SLIDE

# Example of Interpolating Strings

```ruby
puts "1 + 1 = #{1 + 1}"
name = "Jorge"
puts "My Name Is #{name}"
```

!SLIDE

```ruby
task "introduction", [ "name" ] => [ "greetings:formal" ] do |task,params|
  puts "Hi My Name is #{params.name}"
  Rake::Task['goodbye'].invoke
end
```

!SLIDE

# How Do I Use This Parameter?

```
$ rake task[PARAM1,...]
```

!SLIDE

# Example of Usage

```
$ rake introduction[Bilbo]
hello
Hi My Name is Bilbo
goodbye
```

!SLIDE

# Goal

```
$ rake downloads:copy[images]
$ rake downloads:copy[txt]
$ rake downloads:copy[videos]
```

!SLIDE

# Review and Questions
