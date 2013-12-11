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