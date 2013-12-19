!SLIDE title

# Capybara

!SLIDE title

## Gemfile

```ruby
gem 'capybara'
gem "selenium-webdriver", "~> 2.34.0"
```

!SLIDE title commandline

```
$ bundle install
```

!SLIDE

## spec_helper.rb

```ruby
require 'capybara'
require 'capybara/rspec'

Capybara.run_server = false
Capybara.default_driver = :selenium
Capybara.app_host = 'http://192.241.192.185:3001'
# Capybara.app_host = 'http://192.241.192.185:3002'
# Capybara.app_host = 'http://192.241.192.185:3003'
# Capybara.app_host = 'http://192.241.192.185:3004'

RSpec.configure do |config|
  config.include Capybara::DSL
  config.include Capybara::RSpecMatchers
end
```

!SLIDE title

## spec/features/visit_spec.rb

```ruby
require 'spec_helper'

describe "Visit the Webpage" do

  it "view the index page" do
    visit "/"
    expect(page).to have_link("Sign up or Log in")
  end
end
```

!SLIDE title commandline

```
$ rspec spec/features/visit_spec.rb
```

!SLIDE title

# Goal

!SLIDE title commandline

# Write a Spec

```
$ rspec
.

Finished in 0.00115 seconds
1 example, 0 failures
```

!SLIDE title

## Review and Questions