!SLIDE title

# Introduction to Rake

!SLIDE title

Rake is a framework that allows us to express our existing tools and scripts in
a simple logic order.

!SLIDE title

Rake is a Domain Specific Language written in Ruby. When you are using rake,
you are writing all Ruby but with some addition methods defined that allow us
to structure our various tasks and their dependencies.

!SLIDE title commandline

## Running Rake

```
$ rake
```

!SLIDE title

## Creating a Rakefile

```
$ touch Rakefile
```

Also Supported: rakefile; rakefile.rb; Rakefile.rb

!SLIDE title

## Defining a Rake Task

```ruby
task "TASKNAME" do
  # CODE TO MAKE THE TASK GO
end
```

!SLIDE title

## A Little Bit of Ruby

```ruby
puts "MESSAGE"
puts "Hello World"
```

!SLIDE title

## Example Tasks

```ruby
task "hello" do
  puts "hello"
end
```

```ruby
task "goodbye" do
  puts "goodbye"
end
```

!SLIDE title commandline

## Running our Tasks

```
$ rake hello
hello
$ rake goodbye
goodbye
```

!SLIDE title commandline

## Seeing Our Tasks

```
$ rake -T

```

!SLIDE title

## Uh Oh!

Tasks without descriptions do not appear in the list of tasks. They are still
executable, they are simply unlisted.

!SLIDE title

## Task Description

```ruby
desc "Says Hello"
task "hello" do
  puts "hello"
end

desc "Says Goodbye"
task "goodbye" do
  puts "goodbye"
end
```

!SLIDE title commandline

## Seeing Our Tasks

```
$ rake -T
rake hello   # Says Hello
rake goodbye # Says Goodbye
```

!SLIDE title

## A Little Bit More Ruby

```ruby
`OPERATING SYSTEM COMMAND`
```

!SLIDE title

## Backtick Examples

```ruby
puts `ls`
puts `echo hello`
puts `mv source.txt destination.txt`
puts `rm *.txt`
```

!SLIDE title

# Goal

!SLIDE commandline

# Create Rake Task

```
$ rake -T
rake clean  # Deletes all downloaded files
rake copy   # Copies all my txt files to my Desktop
$ rake copy
Moving all text files (.txt) to the Desktop
```

!SLIDE title

## Review and Questions