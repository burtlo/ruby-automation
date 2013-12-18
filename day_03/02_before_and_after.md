!SLIDE title

# Before and After
Setting up and Tearing Down

!SLIDE title

RSpec provides **before** and **after** which allow you to **perform setup and
teardown** for your tests. Before and After comes in two varieties **each**
and **all**.

!SLIDE

## Repetition Of Code

```ruby
describe "Database" do
  it "should respond to adapter" do
    database = Database.new
    expect(database).to respond_to("adapter")
  end

  it "should respond to database" do
    database = Database.new
    expect(database).to respond_to("database")
  end

  it "should respond to user" do
    database = Database.new
    expect(database).to respond_to("user")
  end

  it "should respond to password" do
    database = Database.new
    expect(database).to respond_to("password")
  end
end
```

!SLIDE

## Using a Before

```ruby
describe "Database" do
  before "each" do
    @database = Database.new
  end

  it "should respond to adapter" do
    expect(@database).to respond_to("adapter")
  end

  it "should respond to database" do
    expect(@database).to respond_to("database")
  end

  it "should respond to user" do
    expect(@database).to respond_to("user")
  end

  it "should respond to password" do
    expect(@database).to respond_to("password")
  end
end
```

!SLIDE title

## Using An After

```ruby
describe "Database" do
  before "each" do
    @database = Database.new
    @database.connect
  end

  after "each" do
    @database.disconnect
  end

  # ...
end
```

!SLIDE title

## Remember RSpec Is Ruby

```ruby
describe "Database" do
  before "each" do
    @database = Database.new
  end

  [ "adapter", "database", "user", "password"].each do |method_name|

    it "should respond to #{method_name}" do
      expect(@database).to respond_to(method_name)
    end

  end

end
```

!SLIDE title

# Goal

!SLIDE title commandline text-size-90

# Clean Up Our Spec

* Find the code that is repeated
* Move that code to the before
* Assign that value to an instance variable
* Update all the tests

!SLIDE title

## Review and Questions