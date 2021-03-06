[![Build Status](https://travis-ci.org/amedeiros/area_code_validator.svg)](https://travis-ci.org/amedeiros/dl_validator)

# DlValidator

DlValidator is a small gem that performs soft checks against a drivers license number and state. This is used only to flag a drivers license as being invalid, and is not intended to be considered true denial on a drivers license number.

The valid method is supported in version >= 0.0.5

## Installation

Add this line to your application's Gemfile:

    gem 'dl_validator'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install dl_validator

## Usage

With a drivers license number and drivers license state

```ruby
DlValidator.invalid?('F123456789012', 'FL') => false
DlValidator.invalid?('F7834', 'FL')         => true

DlValidator.valid?('F123456789012', 'FL')   => true
DlValidator.valid?('F7834', 'FL')           => false
```

Inside your rails model. Dependent on fields :drivers_license_number and :drivers_license_state
```ruby
class DriversLicense < ActiveRecord::Base
  attr_accessible :drivers_license_number, :drivers_license_state
  validates :drivers_license_number, :drivers_license_state, :drivers_license_invalid => true
end
```


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Author

Andrew Medeiros, andrew@amedeiros.com, @_AndrewMedeiros

## Contributors
[crstamps2](https://github.com/crstamps2)
[mrryanjohnston](https://github.com/mrryanjohnston)

## Future

Update active model validation to be more flexible with field names.
