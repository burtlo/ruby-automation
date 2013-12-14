!SLIDE

# Command-Line UX/UI

!SLIDE

A fun, useful aside is to spend some time to make our command tools nicer
with some additional gems that format data output and provide ways to ask
for user input.

!SLIDE

# Formatador

This gem provides a simple way to output data in a tabular format.
Bonus: it is also easy to color to your ouput.

!SLIDE

# Add a Dependency to the Gemfile

```
gem 'formatador'
```

!SLIDE

# Install Our Dependencies

```
$ bundle check
$ bundle install
```

!SLIDE

# Update Our Rakefile

```ruby
require 'fileutils'
require 'formatador'
```

!SLIDE

# Sample Output

```ruby
table_data = [ { "name" => "Frank" }, { "name" => "Katrina" } ]
Formatador.display_table(table_data)
```

```
$ rake -T
  +---------+
  | name    |
  +---------+
  | Frank   |
  +---------+
  | Katrina |
  +---------+
...
```

!SLIDE

# Table Data

```ruby
[ { "name" => "Frank" }, { "name" => "Katrina" } ]
```

The following data is an array of hashes!

!SLIDE

# Arrays

```ruby
[ 1, 2, 3, 4 ]
[ 1, "two", 3.0, { "number" => 4 } ]
```

Ruby arrays can contain any types of values that you want, though they
usually contain the same type of thing.

!SLIDE

# Hashes

```ruby
# { KEY => VALUE }
{ "name" => "frank", "age" => 36 }
```

Remember, ENV is a hash, we are simply defining a Hash here. When you define
a Hash you need to specify the key with the corresponding value.

!SLIDE

# Creating a Table With Real Data

```
$ rake downloads:txt:list
  +------------+------+
  | name       | size |
  +------------+------+
  | pets.txt   | 14   |
  +------------+------+
  | houses.txt | 24   |
  +------------+------+
```

!SLIDE

# Breaking Down the Problem

* Create or Find the Rake Task
* Find all the files end with **txt** and determine their size.
* Place all that file data into a hash
* Then place each file hash into an array
* Display the content in a table

!SLIDE

# Create or Find the Rake Task

## Looking for:

* A task named "downloads:txt:list"
* A namespace "downloads" with a task named "txt:list"
* A namespace "downloads", with a namespace "txt", with a task named "list"

!SLIDE

# Find all the files end with **txt**

```ruby
Dir.glob["/Users/frank/Downloads/*.txt"]
Dir["/Users/frank/Downloads/*.txt"]
```

!SLIDE

# Determine their File Size

```ruby
File.size("FILEPATH")
```

!SLIDE

# File Size for Each File

```ruby
Dir["/Users/frank/Downloads/*.txt"].each do |txt_file|
  puts File.size(txt_File)
end
```

But we need to save this data in a hash!

!SLIDE

# Place all that file data into a hash

```ruby
Dir["/Users/frank/Downloads/*.txt"].each do |txt_file|
  file_hash = { "name" => txt_file, "size" => File.size(txt_File) }
end
```

The data is now in a hash, but now we need to store it in an Array!

!SLIDE

# Then place each file hash into an array

```ruby
file_data = []

Dir["/Users/frank/Downloads/*.txt"].each do |txt_file|
  file_hash = { "name" => txt_file, "size" => File.size(txt_File) }
  file_data.push(file_hash)
end
```

Now the `file_data` array has all info for every file

!SLIDE

# Display the content in a table

```ruby
Formatador.display_table(file_data)
```

!SLIDE

# rake downloads:txt:list

```ruby
file_data = []

Dir["/Users/frank/Downloads/*.txt"].each do |txt_file|
  file_hash = { "name" => txt_file, "size" => File.size(txt_File) }
  file_data.push(file_hash)
end

Formatador.display_table(file_data)
```

!SLIDE

# Asking for Input

Up until this point we have relied on parameters and environment varibles
to give us the variables we needed to respond. Sometimes it is useful to
**ask the user for input**. Saving them from having to remember various
parameters.

!SLIDE

# Highline

HighLine was designed to ease the tedious tasks of doing console input and output with low-level methods like gets() and puts()

!SLIDE

# Add a Dependency to the Gemfile

```
gem 'highline'
```

!SLIDE

# Install Our Dependencies

```
$ bundle check
$ bundle install
```

!SLIDE

# Update Our Rakefile

```ruby
require 'fileutils'
require 'formatador'
require 'highline/import'
```

This gem uses a non-standard approach when it comes to using it in your
project.

!SLIDE

# Sample Question

```ruby
favorite_color = ask("What is your favorite color?")
puts "Your favorite color is #{favorite_color}."
```

```
$ rake -T
What is your favorite color?
blue<ENTER>
Your favorite color is blue.
```

!SLIDE

# Sample Question with Default

```ruby
cups_of_coffee = ask("How many cups of coffee do you drink?") do |question|
  question.default = 2
end
puts "You really drink #{cups_of_coffee} cup(s) of coffee?"
```

```
$ rake -T
How many cups of coffee do you drink?  |2|
<ENTER>
You really drink 2 cups of coffee?
```

!SLIDE

# Asking for a Download Location

```
$ rake downloads:copy[txt]
Copy files to which location?  |/Users/frank/Desktop|
/Users/frank/Desktop/ReadLater<ENTER>
Copying pets.txt to /Users/frank/Desktop/ReadLater
Copying houses.txt to /Users/frank/Desktop/ReadLater
```

!SLIDE

# Breaking Down the Problem

* Create or Find the Rake Task
* If the user has not specified an environment variable DESTINATION
* If yes, use that destination
* If no, then lets ask the user for a destination

!SLIDE

# Create or Find the Rake Task

## Looking for:

* A task named "downloads:copy"
* A namespace "downloads" with a task named "copy"

!SLIDE

# Have they already specified a destination?

```ruby
destination = ENV['DESTINATION']

if destination
  # THEY HAVE
else
  # ASK FOR DESTINATION
end

# ... copying code ...
```

!SLIDE

# No Destination Specified

```ruby
destination = ENV['DESTINATION']

if not destination
  # ASK FOR DESTINATION
end

# ... copying code ...
```

!SLIDE

# Asking for a destination

```ruby
destination = ENV['DESTINATION']

if not destination
  destination = ask("Copy files to which location?")
end

# ... copying code ...
```

!SLIDE

# Asking for a destination with Default

```ruby
destination = ENV['DESTINATION']

if not destination
  destination = ask("Copy files to which location?") do |question|
    question.default = "/Users/frank/Desktop"
  end
end

# ... copying code ...
```

!SLIDE

# Goal

```
$ rake downloads:txt:list
  +------------+------+
  | name       | size |
  +------------+------+
  | pets.txt   | 14   |
  +------------+------+
  | houses.txt | 24   |
  +------------+------+
$ rake downloads:txt:show[pets.txt]
Dog
Cat
Iguana
$ rake downloads:txt:show FILE=pets.txt
Dog
Cat
Iguana
$ rake downloads:copy[txt] DESTINATION="/Users/frank/Desktop"
Copying pets.txt to /Users/frank/Desktop
Copying houses.txt to /Users/frank/Desktop
$ rake downloads:copy[txt]
Copy files to which location?  |/Users/frank/Desktop|
/Users/frank/Desktop/ReadLater
Copying pets.txt to /Users/frank/Desktop/ReadLater
Copying houses.txt to /Users/frank/Desktop/ReadLater
```

!SLIDE

# Review and Questions

!SLIDE

* https://github.com/JEG2/highline
* https://github.com/geemus/formatador
