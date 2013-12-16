!SLIDE title

# Section More Rake

!SLIDE

## A New Task

* Says Hello
* Gives Our Name
* Says Goodbye

!SLIDE title

## Something like ...

```ruby
task "introduction" do
  puts "hello"
  puts "Hi My Name is ..."
  puts "goodbye"
end
```

!SLIDE title

## Repetition of Our Existing Tasks

```ruby
task "hello" do
  puts "hello"
end

task "goodbye" do
  puts "goodbye"
end
```

!SLIDE title

## Dependent Task

```ruby
task "introduction" => [ "hello", "goodbye" ] do
  puts "Hi My Name is ..."
end
```

!SLIDE title commandline

## Uh Oh ... Almost

```
$ rake introduction
hello
goodbye
Hi My Name is ...
```

!SLIDE title

## Invoking A Task

```ruby
task "introduction" => [ "hello" ] do
  puts "Hi My Name is ..."
  Rake::Task['goodbye'].invoke
end
```

!SLIDE title commandline

## Much Better

```
$ rake introduction
hello
Hi My Name is ...
goodbye
```

!SLIDE title commandline

## Default Operation

```
$ rake
rake aborted!
Don't know how to build task 'default'
```

!SLIDE title

## Setting a Default

```ruby
task "default" => [ "introduction" ]
```

!SLIDE title commandline

## Nice!

```
$ rake
hello
Hi My Name is ...
goodbye
```

!SLIDE title

## Grouping our Tasks

It is possible that we may be overrun with complexity. We may start to add
several different kinds of greetings and goodbyes. It would be great to
logically group them.

!SLIDE title

## Namespaces

```ruby
namespace "NAMESPACE-NAME" do
  task "TASKNAME" do
     # CODE TO MAKE THE TASK GO
  end
end
```

!SLIDE title

## Kinds of Greetings

```ruby
namespace "greetings" do

  desc "Good for when saying hi to new people or when talking with my Mom"
  task "formal" do
    puts "hello"
  end

  desc "Good for talking greeting friends"
  task "familiar" do
    puts "yo"
  end
end
```

!SLIDE title commandline

## rake namespace:task

```
$ rake -T
rake greetings:familiar  # Good for talking greeting friends
rake greetings:formal    # Good for when saying hi to new people or when talking with my Mom
...
$ rake greetings:formal
hello
$ rake greetings:familiar
yo
```

!SLIDE title

# Goal

!SLIDE commandline

# Create More Rake Tasks

```
$ rake -T
rake downloads:list   # (default) List all the files in the downloads directory
rake downloads:clean  # Deletes all downloaded files
rake downloads:txt:copy   # Copies all my txt files to my Desktop
$ rake
Document.txt
AnotherDocument.txt
$ rake downloads:txt:copy
Document.txt
AnotherDocument.txt
Moving all text files (.txt) to the Desktop
$ rake copy
Document.txt
AnotherDocument.txt
Moving all text files (.txt) to the Desktop
```

!SLIDE title

## Review and Questions