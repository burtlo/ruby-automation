!SLIDE title

# RSpec
Behavior Driven Development

!SLIDE title

**BDD** is an approach to software development that **combines Test-Driven
Development, Domain Driven Design**, and **Acceptance Test-Driven Planning**.
RSpec **helps you do the TDD part of that equation**, focusing on the
documentation and design aspects of TDD.

!SLIDE title

## Install Rspec

```
$ gem install rspec
```

```ruby
gem 'rspec'
```

!SLIDE commandline

## Running RSpec

```
$ rspec
...
cannot load such file -- /file/path/spec (LoadError)
...
```

An error. What gives?

!SLIDE title

## Running Rspec The Right Way

```
$ mkdir spec
$ rspec
```

Rspec expects a `spec` directory for all its spec files.

!SLIDE title commandline

## Creating Our First Spec File

```
$ touch spec/first_spec.rb
```

!SLIDE title

## Writing Our First Spec

```ruby
describe "Ruby Addition" do

end
```

!SLIDE title

## Writing Our First Spec

```ruby
describe "Ruby Addition" do
  it "1 + 1 equals 2" do

  end
end
```

!SLIDE title

## Writing Our First Expectation

```ruby
describe "Ruby Addition" do
  it "1 + 1 equals 2" do
    result = 1 + 1
    expect(result).to(eq(2))
  end
end
```

!SLIDE title

## An Older Way of Writing Expectations

```ruby
result.should(eq(2))
```

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