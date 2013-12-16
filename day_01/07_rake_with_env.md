!SLIDE title

# Rake With Environment Variables

!SLIDE title

Often times our tools need to take inputs that allow us to do a similar
operation with different parameters. Lets look at providing inputs to our
rake tasks.

!SLIDE title commandline

## The "Real Talk" about Rake Parameters

Not many people use rake parameters and most people do not know them. People
often use **environment variables** as parameters.

!SLIDE title

## Imagine You Wanted ...

```
Good Morning
Hi My Name is Bilbo
goodbye
```

```
Good Evening
Hi My Name is Bilbo
goodbye
```

!SLIDE title

## Add the Parameter to the Original Task

```ruby
task "introduction", ["name","time_of_day"] => [ "greetings:formal" ] do |task,params|
  puts "Hi My Name is #{params.name}"
  Rake::Task['goodbye'].invoke
end
```

!SLIDE title

## Also Update the Dependent Task as Well

```ruby
namespace "greetings" do
  task "formal", "time_of_day" do |task,params|
    if params.time_of_day
      puts "Good #{params.time_of_day}"
    else
      puts "hello"
    end
  end

  #...
end
```

!SLIDE title

## Instead Use Environment Variables

This is what the majority of rake tools use to pass data from the command-line
to scripts.

!SLIDE title

## How do I get the value of environment variables?

!SLIDE title

## Ruby defines ENV

**ENV** is a *global* Hash available within Ruby scripts.

!SLIDE title

## Example of Accessing ENV Variables

```ruby
puts ENV["HOME"]        # => "/Users/burtlo"
puts ENV["UNDEFINED KEY"] # => ""
```

!SLIDE title

## Our Task Using ENV

```ruby
namespace "greetings" do
  task "formal" do
    if ENV["TIME_OF_DAY"]
      puts "Good #{ENV["TIME_OF_DAY"]}"
    else
      puts "hello"
    end
  end
end
```

!SLIDE title commandline

## How Do I Specify an ENV Varaiable?

```
$ rake task[PARAM1,...] VARIABLE=VALUE
```

!SLIDE title commandline

## Example Usage

```
$ rake introduction[Bilbo] TIME_OF_DAY=Morning
Good Morning
Hi My Name is Bilbo
goodbye
```

!SLIDE title

# Goal

!SLIDE

# Add ENV["DESTINATION"]

```
$ rake downloads:copy[images]
$ rake downloads:copy[txt]
$ rake downloads:copy[videos] DESTINATION=/Users/Frank/Desktop/WatchLater
```

!SLIDE title

## Review and Questions
