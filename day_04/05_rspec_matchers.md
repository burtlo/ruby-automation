!SLIDE title

# Custom RSpec Matchers
when the base matchers are not enough

!SLIDE title

## Several Expectations

```ruby
expect(page).to have_text("Logged in as")
expect(page).to have_link("Account Profile")
expect(page).to have_link("Log Out")
```

!SLIDE title

## We could have done something like ...

```ruby
result = page.has_text?("Logged in as") and
         page.has_link?("Account Profile") and
         page.has_link?("Log out")

expect(result).to_be(true)
```

But the error failed expectation would not give us much information

!SLIDE title

## Custom Error Message

```ruby
expect(false).to(be(true),"Custom Error Message")
```

!SLIDE

## Crafting My Own Error

```ruby
has_logged_in_text = page.has_text?("Logged in as")
has_account_profile_link = page.has_link?("Account Profile")
has_log_out_link = page.has_link?("Log out")

error_message = ""

unless has_logged_in_text
  error_message += "'Missing Logged in as ...' text "
end

unless has_account_profile_link
  error_message += "No 'Account Profile' link "
end

unless has_log_out_link
  error_message += "No 'Log out' link "
end
```

!SLIDE

```ruby

result = has_logged_in_text and
         has_account_profile_link and
         has_log_out_link

expect(result).to(be(true),error_message)

```

!SLIDE title

## Dream Driven Development

```
expect(page).to have_a_logged_in_nav_bar
```

!SLIDE

## Define the Method

```ruby
def have_a_logged_in_nav_bar
  # What Do I Return?
end
```

!SLIDE

## Define a New Instance

```ruby
def have_a_logged_in_nav_bar
  LoggedInNavBar.new
end
```

!SLIDE

## Define the Matcher Class

```ruby
def have_a_logged_in_nav_bar
  LoggedInNavBar.new
end

class LoggedInNavBar
  def matches?(page)
    # CHECK PAGE FOR THINGS HERE
    # return true if all things are there
    # return false if something is not there
    return true
  end

  def failure_message_for_should
    "It is missing all those things you want Sorry!"
  end

  def failure_message_for_should_not
    "It has all those things you don't want it to have! Sorry!"
  end
end
```

!SLIDE

## matches?

```ruby
def matches?(page)
  has_logged_in_text = page.has_text?("Logged in as")
  has_account_profile_link = page.has_link?("Account Profile")
  has_log_out_link = page.has_link?("Log out")

  @error_message = ""

  unless has_logged_in_text
    @error_message += "'Missing Logged in as ...' text "
  end

  unless has_account_profile_link
    @error_message += "No 'Account Profile' link "
  end

  unless has_log_out_link
    @error_message += "No 'Log out' link "
  end

  has_logged_in_text and has_account_profile_link and has_log_out_link
end
```

!SLIDE

```ruby
def failure_message_for_should
  @error_message
end
```

!SLIDE title

# Goal

!SLIDE title

# Write a Custom Matcher

!SLIDE title

## Review and Questions