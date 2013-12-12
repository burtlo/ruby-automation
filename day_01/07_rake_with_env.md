!SLIDE

# Rake With Environment Variables

!SLIDE

Often times our tools need to take inputs that allow us to do a similar
operation with different parameters. Lets look at providing inputs to our
rake tasks.

!SLIDE

# The "Real Talk" about Rake Parameters

Not many people use rake parameters and most people do not know them. People
often use **environment variables** as parameters.

!SLIDE

# Imagine You Wanted ...

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

!SLIDE

# Add the Parameter to the Original Task

```ruby
task "introduction", ["name","time_of_day"] => [ "greetings:formal" ] do |task,params|
  puts "Hi My Name is #{params.name}"
  Rake::Task['goodbye'].invoke
end
```

!SLIDE

# Also Update the Dependent Task as Well

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

!SLIDE

# Instead Use Environment Variables

This is what the majority of rake tools use to pass data from the command-line
to scripts.

!SLIDE

# How do I get the value of environment variables?

!SLIDE

# Ruby defines ENV

**ENV** is a *global* Hash available within Ruby scripts.

!SLIDE

# Example of Accessing ENV Variables

```ruby
puts ENV["HOME"]        # => "/Users/burtlo"
puts ENV["UNDEFINED KEY"] # => ""
```

!SLIDE

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

!SLIDE

# How Do I Specify an ENV Varaiable?

```
$ rake task[PARAM1,...] VARIABLE=VALUE
```

!SLIDE

# Example of Usage

```
$ rake introduction[Bilbo] TIME_OF_DAY=Morning
Good Morning
Hi My Name is Bilbo
goodbye
```

!SLIDE

# Goal

```
$ rake copy[images]
$ rake copy[txt]
$ rake copy[videos] DESTINATION=/Users/Frank/Desktop/WatchLater
```

!SLIDE

# Review and Questions
