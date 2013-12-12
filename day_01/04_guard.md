!SLIDE

# Guard

Reacting to changes on your file system

!SLIDE

# Gems

At this point we have used everything that comes standard with Ruby. This is the
first time we are going to download an additional tool from the internet. Ruby
comes equipped with a tool that allows us to download libraries from the command-line.

!SLIDE

# Gem

```
$ gem -v
2.1.9
$ gem help
```

!SLIDE

# List All Installed Gems

```
$ gem list
```

!SLIDE

# Installing a New Gem

```
$ gem install GEMNAME
```

!SLIDE

# Installing the Guard-Shell Gem

```
$ gem install guard-shell
Fetching: timers-1.1.0.gem (100%)
Successfully installed timers-1.1.0
Fetching: celluloid-0.15.2.gem (100%)
Successfully installed celluloid-0.15.2
Fetching: rb-fsevent-0.9.3.gem (100%)
Successfully installed rb-fsevent-0.9.3
Fetching: rb-inotify-0.9.2.gem (100%)
Successfully installed rb-inotify-0.9.2
Fetching: listen-2.4.0.gem (100%)
Successfully installed listen-2.4.0
Fetching: guard-2.2.4.gem (100%)
Successfully installed guard-2.2.4
Fetching: guard-shell-0.5.2.gem (100%)
Successfully installed guard-shell-0.5.2
7 gems installed
```

!SLIDE

# Setting Up Guard

```
$ guard init shell
```

!SLIDE

# Guardfile

```ruby
# Add files and commands to this file, like the example:
#   watch(%r{file/path}) { `command(s)` }
#
guard :shell do
  watch(/(.*).txt/) {|m| `tail #{m[0]}` }
end
```

!SLIDE

# Uh Oh! Regular Expressions

```ruby
lame_regex = /I am a Regular Expression/
another_lame_regex = %r{I am a Regular Expression}
```

!SLIDE

# Specifying a File Matcher

```ruby
all_text_files = %r{/Users/frank/Downloads/.+\.txt}
all_gif_files = %r{/Users/frank/Downloads/.+\.gif}
most_jpg_files = %r{/Users/frank/Downloads/.+\.jpg}
all_png_files = %r{/Users/frank/Downloads/.+\.png}
all_image_files = %r{/Users/frank/Downloads/.+\.(gif|jpg|png)}
```
!SLIDE

# Rubular

rubular.com

!SLIDE

# Putting it All Together

```ruby
guard :shell do
  watch(%r{/Users/frank/Downloads/.+\.txt}) {|m| `rake downloads:txt:copy` }
end
```
!SLIDE

# Goal

!SLIDE

# Guarding

* Run `guard` to start watching for file changes

* Whenever you create a text file, movie file, and image file the
  appropriate rake action to copy the files is executed.

!SLIDE

# Review and Questions