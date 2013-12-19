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

!SLIDE title

## Crafting My Own Error

```ruby
has_logged_in_text = page.has_text?("Logged in as")
has_account_profile_link = page.has_link?("Account Profile")
has_log_out_link = page.has_link?("Log out")

unless has_logged_in_text
  error_message = "'Missing Logged in as ...' text "
end

unless has_account_profile_link
  error_message = "No 'Account Profile' link "
end

unless has_log_out_link
  error_message = "No 'Log out' link "
end

result = has_logged_in_text and
         has_account_profile_link and
         has_log_out_link

expect(false).to(be(true),error_message)
```

!SLIDE title

## Dream Driven Development

```
expect(page).to have_a_logged_in_nav_bar
```

!SLIDE title

# Goal

!SLIDE title

# Write a Custom Matcher

!SLIDE title

## Review and Questions