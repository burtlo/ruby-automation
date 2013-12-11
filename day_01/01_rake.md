!SLIDE

# Introduction to Rake

!SLIDE

Rake is a framework that allows us to express our existing tools and scripts in
a simple logic order.

!SLIDE

Rake is a Domain Specific Language written in Ruby. When you are using rake,
you are writing all Ruby but with some addition methods defined that allow us
to structure our various tasks and their dependencies.

!SLIDE

# Running Rake

```
$ rake
```

!SLIDE

# Creating a Rakefile

```
$ touch Rakefile
```

Also Supported: rakefile; rakefile.rb; Rakefile.rb

!SLIDE

# Defining a Rake Task

```ruby
task "TASKNAME" do
  # CODE TO MAKE THE TASK GO
end
```

!SLIDE

# A Little Bit of Ruby

```ruby
puts "MESSAGE"
puts "Hello World"
```

!SLIDE

# Example Tasks

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

!SLIDE

# Running our Tasks

```
$ rake hello
hello
$ rake goodbye
goodbye
```

!SLIDE

# Seeing Our Tasks

```
$ rake -T

```

!SLIDE

# Uh Oh!

Tasks without descriptions do not appear in the list of tasks. They are still
executable, they are simply unlisted.

!SLIDE

# Task Description

```
desc "Says Hello"
task "hello" do
  puts "hello"
end

desc "Says Goodbye"
task "hello" do
  puts "goodbye"
end
```

!SLIDE

# Seeing Our Tasks

```
$ rake -T
rake hello   # Says Hello
rake goodbye # Says Goodbye
```

!SLIDE

# A Little Bit More Ruby

```ruby
`OPERATING SYSTEM COMMAND`
```

!SLIDE

# Backtick Examples

```ruby
puts `ls`
puts `echo hello`
puts `mv source.txt destination.txt`
puts `rm *.txt`
```

# Goal

!SLIDE

# Create Rake Task

```
$ rake -T
rake clean  # Deletes all downloaded files
rake copy   # Copies all my txt files to my Desktop
$ rake copy
Moving all text files (.txt) to the Desktop
```

!SLIDE

# Review and Questions

!SLIDE

# More Information

http://mentalized.net/journal/2010/03/08/5_ways_to_run_commands_from_ruby/