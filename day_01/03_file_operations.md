!SLIDE title

# Ruby File Operations

!SLIDE title

## Common File Operations

File operations often require for us to ensure files exist. Ruby provides several tools to make our work easier.

!SLIDE title

## File.exists?(filepath)

```ruby
puts File.exists?("Rakefile") # => true
puts File.exists?("unknown_file.rb") # => false
```

!SLIDE title

## Dir.exists?(dirpath)

```ruby
puts Dir.exists?("Desktop") # => false
puts Dir.exists?("/Users/frank/Desktop") # => true
puts Dir.exists?("/Users/frank/UnknownFolder") # => false
```

!SLIDE title

## Ruby: if AND else

```ruby
if Dir.exist?("/Users/frank/Desktop")
  puts "Copying txt files to the Desktop"
  `cp /Users/frank/Downloads/*.txt /Users/frank/Desktop`
else
  puts "Desktop is Missing - Will Not Copy Files"
end
```

!SLIDE title

## Ruby: if not AND ! (bang) OR unless

```ruby
if not Dir.exist?("/Users/frank/Movies")
  puts "Creating a Movies folder"
  `mkdir /Users/frank/Movies`
end

if ! Dir.exist?("/Users/frank/Movies")
  puts "Creating a Movies folder"
  `mkdir /Users/frank/Movies`
end

unless Dir.exist?("/Users/frank/Movies")
  puts "Creating a Movies folder"
  `mkdir /Users/frank/Movies`
end
```

!SLIDE title

## FileUtils

When you want to do more than check for files and look at file information. This
additional library, packaged with Ruby (but not automatically loaded), provides
you with common, platform agnostic, utilities to do things like: copy files;
move files; delete files; etc.

!SLIDE title

## Loading Up FileUtils

```ruby
require 'fileutils'
```

!SLIDE title

## Replacing our backticks with FileUtils

```ruby
if not Dir.exist?("/Users/frank/Movies")
  puts "Creating a Movies folder"
  # `mkdir /Users/frank/Movies`
  FileUtils.mkdir("/Users/frank/Movies")
end

# ... or ...

FileUtils.mkdir_p("/Users/frank/Movies")
```

!SLIDE title

## More Information

## http://rubydoc.info/stdlib/fileutils/frames

!SLIDE title

# Goal

!SLIDE commandline

# More File Type Sorting

Use FileUtils instead of the backticks you used previously

```
$ rake -T
rake downloads:list          # (default) List all the files in the downloads directory
rake downloads:clean         # Deletes all downloaded files
rake downloads:txt:copy      # Copies all my txt files to my Desktop
rake downloads:movies:copy   # Copies all my movie files to my Movies
rake downloads:images:copy   # Copies all my movie files to my Images
```

!SLIDE title

## Review and Questions