!SLIDE

# Managing Dependencies With Bundler

!SLIDE

Sharing this code we have created now comes with the additional instructions
that you must first install **guard-shell** if you want to use it. Later if we
add more dependencies we would have more to install.

!SLIDE

# Bundler

```
$ gem install bundler
```

!SLIDE

# We Need a Gemfile

```
touch Gemfile
```

!SLIDE

# Setting a Source

```ruby
source "https://rubygems.org"
# source "http://internal-server.ourcompany.it"
```

!SLIDE

# Adding our Gems

```ruby
source "https://rubygems.org"

# gem "NAME OF GEM"
gem "guard-shell"
```

!SLIDE

# Checking Our Dependencies

```
$ bundle check
Resolving dependencies...
The Gemfile's dependencies are satisfied
```

!SLIDE

# Installing Needed Dependencies

```
$ bundle install
Using timers (1.1.0)
Using celluloid (0.15.2)
Using coderay (1.0.9)
Using ffi (1.6.0)
Using formatador (0.2.4)
Using rb-fsevent (0.9.3)
Using rb-inotify (0.9.2)
Using listen (2.4.0)
Using lumberjack (1.0.3)
Using method_source (0.8.1)
Using slop (3.4.5)
Using pry (0.9.12.2)
Using thor (0.18.1)
Using guard (2.2.4)
Using guard-shell (0.5.2)
Using bundler (1.3.5)
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
```

!SLIDE

# What is Gemfile.lock?

```
GEM
  remote: https://rubygems.org/
  specs:
    celluloid (0.15.2)
      timers (~> 1.1.0)
    coderay (1.0.9)
    ffi (1.6.0)
    formatador (0.2.4)
    guard (2.2.4)
      formatador (>= 0.2.4)
      listen (~> 2.1)
      lumberjack (~> 1.0)
      pry (>= 0.9.12)
      thor (>= 0.18.1)
```

!SLIDE

# More about the Gemfile.lock?

```
    ...
    slop (3.4.5)
    thor (0.18.1)
    timers (1.1.0)

PLATFORMS
  ruby

DEPENDENCIES
  guard-shell
```

!SLIDE

# Goal

```
$ ls
Gemfile
Gemfile.lock
$ bundle check
Resolving dependencies...
The Gemfile's dependencies are satisfied
```

!SLIDE

# Review and Questions

!SLIDE

# More Information

http://bundler.io/
