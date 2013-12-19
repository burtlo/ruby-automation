## Day 1 - Ruby as a Tool

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

* Rake
* Guard
* Bundler
* Gem

We want to interact with our scripts through: command-line input; command-line parameters; environment variables; and files.

* ENV
* ARGV
* Kernel.gets
* Ruby Core: File
* Ruby Core: Dir

Let's finish our first day of tools creation with some gems that will make our
life easier when making command-line tools by generating a better looking
interface and generating better fake data.

* Highline
* Formatador

### Resources

* http://jasonseifer.com/2010/04/06/rake-tutorial
* https://github.com/guard/guard
* https://github.com/guard/guard-shell
* https://github.com/guard/guard-livereload
* https://github.com/geemus/formatador
* http://www.awesomecommandlineapps.com/gems.html
* https://github.com/JEG2/highline
* http://rubydoc.info/stdlib/core/Kernel:gets
* http://rubular.com/
* http://rubydoc.info/stdlib/fileutils/frames
* http://bundler.io/
http://stackoverflow.com/questions/825748/how-do-i-pass-command-line-arguments-to-a-rake-task
http://patorjk.com/software/taag/#p=display&f=Graffiti&t=Type%20Something%20

## Day 2 - Files and Services

We want to build on the tools that we created yesterday, extending them to
talk to various file formats and start to use different sources and services for them.

* Parsing YAML files
* Parsing JSON
* Parsing CSV files
* Parsing XML with Nokogiri

Using Sinatra we can create simple interfaces that allow us to mock up existing
services. So we will solve the same problem we just solved but solve it again
through API endpoints

* Sinatra
* Faraday
* HTTParty

The data that we have received can get really messy. We want to explore various
ways that we can structure that data to make it easier for us to manage.

* Struct
* OpenStruct
* Custom Classes

With the remaining time in the day we will create our own command-line client
tool (when Rake just won't do). That allows us to specify our own custom
commands and arguments.

* Thor

### Resources

* http://www.awesomecommandlineapps.com/gems.html
* http://www.yaml.org/YAML_for_ruby.html
* http://pro.jsonlint.com/
* http://rubydoc.info/stdlib/csv/frames
* http://nokogiri.org/
* http://www.sinatrarb.com/
* https://github.com/lostisland/faraday
* https://github.com/jnunemaker/httparty
* http://rubydoc.info/stdlib/core/Struct
* http://rubydoc.info/stdlib/ostruct/frames
* https://github.com/dam5s/happymapper
* https://github.com/erikhuda/thor

## Day 3 - Databases and Data Structures

Now that we're starting feeling comfortable with Ruby and various tools, let's
start to focus on testing with RSpec. We will also expand our tools to talk to
multiple databases.

* Patterns for effective tests
* How tests go wrong

* Talking to a database with ActiveRecord
* Talking to a multiple databases
* Modeling tables that don't fit the ActiveRecord paradigm (table names, different primary keys, composite primary keys)
* Gaining access to the raw connection and writing SQL
* Knowing the limitations of ActiveRecord (namely speed)

### Ideas

* Convert an existing warm up tests to RSpec
* Cleaning up Rspec tests with explicit/implicit subject
* Create test suite for our API functionality that we create yesterday.
* Breaking apart code over mocking and stubbing

### Resources

* http://guides.rubyonrails.org/active_record_basics.html
* http://guides.rubyonrails.org/migrations.html
* http://guides.rubyonrails.org/active_record_validations.html
* http://guides.rubyonrails.org/active_record_callbacks.html
* http://guides.rubyonrails.org/association_basics.html
* http://guides.rubyonrails.org/active_record_querying.html
* https://github.com/composite-primary-keys/composite_primary_keys
* https://www.relishapp.com/rspec/

## Day 4 - Testing the Web with RSpec + Capybara

Testing local code is relatively easy, let’s move on to the web. We’ll use the Capybara library to connect RSpec to a virtual web browser.

* Basics of Capybara syntax
* Thinking about the flow of operations
* Using the default Rack::Test adapter
* Replacing Rack::Test with Selenium
* Replacing Rack::Test with Poltergeist
* Using VCR to mock remote services
* Parsing HTML with Nokogiri

### Setup

* Configuring Capybara with Rails and outside of Rails
* how to find elements on the page
* troubleshooting techniques
* save_and_open_page
* Using js: true to launch with Selenium

## Day 5 - Automation Tools & Practices

## Missing

* Cucumber
* Capistrano
* SSH
* FTP
* Threading, Forking and Processes
* backticks, %x{}, system, and popen
* YAML anchors & erb
* pry
* bundle open
* Faker
* Parsing XML with Happymapper
* Hashie
* Ruby - Optional Parameters, Named Parameters, Splats, Monkey Patching
* Ruby - Block Initializers, instance_eval, instance_exec
* Domain Specific Languages

### Windows Resources

* https://github.com/adoxa/ansicon