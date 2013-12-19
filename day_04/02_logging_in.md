!SLIDE title

# Logging In

!SLIDE

## spec/features/login_spec.rb

```ruby
require 'spec_helper'

describe "User Login" do
  it "able to login" do
    visit "/"
  end
end
```

!SLIDE

## spec/features/login_spec.rb

```ruby
require 'spec_helper'

describe "User Login" do
  it "able to login" do
    visit "/"
    click_link "Sign up or Log in"
  end
end
```

!SLIDE

## spec/features/login_spec.rb

```ruby
require 'spec_helper'

describe "User Login" do
  it "able to login" do
    visit "/"
    click_link "Sign up or Log in"
    fill_in "Email", with: "demo+franklin@jumpstartlab.com"
    fill_in "Password", with: "password"
  end
end
```

!SLIDE

## spec/features/login_spec.rb

```ruby
require 'spec_helper'

describe "User Login" do
  it "able to login" do
    visit "/"
    click_link "Sign up or Log in"
    fill_in "Email", with: "demo+franklin@jumpstartlab.com"
    fill_in "Password", with: "password"
    click_button "Log In"
  end
end
```

!SLIDE

## What's Ambigous?

!SLIDE

## Troubleshooting

* Walk through the page manually
* `save_and_open_page`
* Debugging with `pry`

!SLIDE title

## Walk through the page manually

!SLIDE

## save_and_open_page

```ruby
require 'spec_helper'

describe "User Login" do
  it "able to login" do
    visit "/"
    click_link "Sign up or Log in"
    save_and_open_page
    fill_in "Email", with: "demo+franklin@jumpstartlab.com"
    fill_in "Password", with: "password"
    click_button "Log In"
  end
end
```

!SLIDE title

## Inspect the Saved File

!SLIDE title

## Looking Within the Form

The form has the id `login-form`.

!SLIDE

## Using `within`

Within uses CSS Selectors to specify scoping. '#' prefix to represent id values. '.' prefix to represent class values.

```ruby
within "#element-id" do
  # ... click things ...
end

within ".element-class" do
  # .... click things ...
end
```

!SLIDE

## Using `within`

```ruby
require 'spec_helper'

describe "User Login" do
  it "am able to login" do
    visit "/"
    click_link "Sign up or Log in"

    within "#login-form" do
      fill_in "Email", with: "demo+franklin@jumpstartlab.com"
      fill_in "Password", with: "password"
      click_button "Log In"
    end

  end
end
``

!SLIDE title

## Debugging with `pry`

!SLIDE title

## Update Gemfile

```ruby
gem 'pry'
```

!SLIDE title

## Update spec_helper.rb

```ruby
require 'pry'
```

!SLIDE

## binding.pry

```ruby
require 'spec_helper'

describe "User Login" do
  it "able to login" do
    visit "/"
    click_link "Sign up or Log in"

    binding.pry

    fill_in "Email", with: "demo+franklin@jumpstartlab.com"
    fill_in "Password", with: "password"
    click_button "Log In"
  end
end
```

!SLIDE

## Alternative Solution

There are many ways to find elements, `pry` allows
us to experiment within our specs.

```ruby
it "am able to login" do
  visit "/"
  click_link "Sign up or Log in"
  fill_in "email", with: "demo+franklin@jumpstartlab.com"
  fill_in "password", with: "password"
  click_button "Log In"
end
```

!SLIDE title

## Did Everything Work?

We need to make assertions...

```ruby
expect(page).to have_text("Logged in as")
expect(page).to have_link("Account Profile")
expect(page).to have_link("Log out")
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