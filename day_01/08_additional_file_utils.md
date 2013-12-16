!SLIDE title

# Additional File Utilities

!SLIDE title

There are still some very common file utilities that we need to look at before
we say goodbye, for now, to our command-line tools. We need to be able to open
a file, read its contents, and even find a list of files.

!SLIDE title

## File.open

```ruby
file = File.open("FILEPATH","MODETYPE")
# ...
```

Modes: "r"; "r+"; w"; "w+", "a", "a+"
Types: "b"; "t"

!SLIDE title

## File.read

```ruby
file_contents = File.read("FILEPATH")
puts file_contents
```

!SLIDE title

## Finding Multiple Files

```ruby
File.exist?("first.txt")
File.exist?("second.txt")
File.exist?("third.txt")
```

!SLIDE title

## Dir.glob

```ruby
text_files = Dir.glob("*.txt")

text_files.each do |text_file|
  File.exist?(text_file)
end
```

!SLIDE title

## What is each?

Each is an **Enumerable** method that allows us to iterate through each element
in a list.

!SLIDE title

## You might be familiar with ...

```
for (int i < 0; i < text_files.length; i++) {
  var text_file = text_files[i];
  // ...
}
```

```
foreach (text_file in text_files) {
  // ...
}
```

!SLIDE title

## Dir.glob

```ruby
text_files = Dir.glob("*.txt")

text_files.each do |text_file|
  puts "Copying #{text_file}"
  FileUtils.cp(text_file,"/Users/frank/Desktop")
end
```

!SLIDE title

## Dir.glob() is the same as Dir[]

```ruby
text_files = Dir.glob("*.txt")
```

```ruby
text_files = Dir["*.txt"]
```

!SLIDE title

# Goal

!SLIDE commandline

## Use File.read, Dir[], and File.exist?

```
$ rake downloads:txt:list
$ rake downloads:txt:show[pets.txt]
Dog
Cat
Iguana
$ rake downloads:txt:show FILE=pets.txt
Dog
Cat
Iguana
$ rake downloads:copy[txt]
Copying pets.txt
Copying houses.txt
...
```

!SLIDE title

## Review and Questions