!SLIDE title

# Testing An Entire Purchase

# Goal

!SLIDE title commandline

# Write a Spec

```
$ rspec
.

Finished in 0.00115 seconds
1 example, 0 failures
```

!SLIDE

```ruby
require 'spec_helper'

describe "User Login" do
  it "able to purchase" do
    visit "/"
    click_link "Albuquerque"
    click_link "Ono Burrito10"

    # Maybe too brittle
    # within "#item_104" do
    #   click_button "Add to Cart"
    # end

    items = page.all("div.item")
    first_item = items.first
    first_item.click_button "Add to Cart"

    items = page.all("div.item")
    last_item = items.last
    last_item.click_button "Add to Cart"

    click_link "View Your Order"

    click_button "Checkout"

    binding.pry

    within("#new_address") do
      fill_in "First name", :with => "Franklin"
      fill_in "Last name", :with => "Webber"
      fill_in "Street address", :with => "220 Magnolia St"
      fill_in "City", :with => "Denver"
      fill_in "State", :with => "CO"
      fill_in "Zipcode", :with => "80220"
      fill_in "address[email]", :with => "franklin.webber@gmail.com"
      click_button "Use This Billing Address"
    end

    click_button "Pay with Card"
  end
end
```

!SLIDE title

## Review and Questions