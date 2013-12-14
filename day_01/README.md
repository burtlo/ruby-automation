# Day 1 - Ruby as a Tool

Before we launch into using Ruby lets first use Ruby to automate some simple
tasks and scripts. We will forgo the classic introduction to Ruby syntax at
the start and understand how we can use various tools within the ruby
eco-system to make testing easier.

> While we are not focusing on the Ruby language, we will be working on
> exercises that will bring us in contact with the Ruby language in
> convert and overt ways. We will definitely stop and discuss core essential
> Ruby syntax as we use it to solve real problems.

Lets start with a number of fundamental tools of a Ruby toolchain. We will
use these tools in various exercises to see how Ruby can help us immediately
solve problems and reduce complexity of our tools and processes.

## 01 - Rake

Use rake we will copy a file from our downloads location to another location on
our file system.

* Commands `task`, `desc`, and `namespace`
* Use of Ruby `puts` and the backticks to execute a command
* rake commands `rake -T`

## 02 - More Rake

Lets continue to expand our example to find out more guards and checks for
the presence of the file and the ext name of the file. We also want to find
all files that match the specified file path type and if the path exists. If
intended sources or destinations don't exist we'll make them

* Task Dependency
* Invoking Tasks
* Task Namespaces
* Default Task

## 03 - Core File Operations

We can use backticks to get quite a bit done. However, there are utilities
within Ruby that allow us to do a lot of file and directory checking.

* if
* Ruby Core: File - exists?, file?, dir?, basename? extname?
* Ruby Core: Dir - exists?, Globs [**/*.zip]
* FileUtils to make our directories and do our dirty work: `cp`, `mkdir_p`

## 04 - Guard

Now that we have our task in place, it is cumbersome to have to execute it
manually. Using guard we can define a Guardfile have the code execute when any
new file is added to our folder.

* Gem installation: guard and guard-shell
* Guard init
* Guard syntax: `guard`, `watch`
* Crash Course: Regular Expressions

## 05 - Bundler

Our test tools now have some dependencies so we want to track those dependencies
and make it easier for us to install the components we need when we go to a new
system.

* Gemfile syntax: `source`, `gem`
* bundle commands: `install`, `update`, `check`
* Gemfile and Gemfile.lock

## 06 - Rake with Parameters

We want to interact with our scripts through parameters.

* Rake parameters

## 07 - Rake with Environment Variables

We want to interact with our scripts through environment variables.

* ENV
* Ruby Core: Hash

## 08 - Some Additional File Utilities

Lets finish up our rake requirements by looking at pulling in data from
our environment variables and additional information from files.

* Ruby Core: File.open, File.read, File.extname
* Dir globs

## 09 - Command-Line UX/UI

Let's finish our first day of tools creation with some gems that will make our
life easier when making command-line tools by generating a better looking
interface and generating better fake data.

* Highline - `say`, `ask`
* Formatador

Both of these gems make it easier and more interesting to ask for input and
generate output. This is useful if we wanted to create great tools for
ourselves that provide better feedback or provide more interaction.

### Resources

* http://jasonseifer.com/2010/04/06/rake-tutorial
* http://mentalized.net/journal/2010/03/08/5_ways_to_run_commands_from_ruby/
* http://stackoverflow.com/questions/825748/how-do-i-pass-command-line-arguments-to-a-rake-task
* https://github.com/guard/guard
* https://github.com/guard/guard-shell
* https://github.com/guard/guard-livereload
* http://www.awesomecommandlineapps.com/gems.html
* https://github.com/JEG2/highline
* https://github.com/geemus/formatador
* http://rubydoc.info/stdlib/core/Kernel:gets
* http://rubular.com/
* http://rubydoc.info/stdlib/fileutils/frames
* http://patorjk.com/software/taag/#p=display&f=Graffiti&t=Type%20Something%20