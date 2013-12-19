!SLIDE title

# RSpec With Guard
Tired of Running the Same Command

!SLIDE title commandline

## Too Lazy to Keep Re-Running

```
$ rspec spec/features/login_spec.rb
$ rake spec
```

!SLIDE title

## Gemfile

```ruby
gem 'guard-rspec'
```

!SLIDE title commandline

## Add RSpec Guarding To Our Guardfile

```
$ guard init rspec
```

!SLIDE title

## Just What We Need

```ruby
guard :rspec do
  watch(%r{^spec/.+_spec\.rb$})
  watch('spec/spec_helper.rb')  { "spec" }
end
```

!SLIDE title commandline

## Start Guard

```
$ guard
```

!SLIDE title

## Pry Again?

That prompt that guard gives you is actually pry.

!SLIDE title

# Goal (optional)

!SLIDE commandline

# Run Guard

```
$ guard
```

* Make a change to one of your spec files
* Watch the guard run your tests

!SLIDE title

## Review and Questions