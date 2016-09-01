[![Gem Version](https://badge.fury.io/rb/schema_plus_compatibility.svg)](http://badge.fury.io/rb/schema_plus_compatibility)
[![Build Status](https://secure.travis-ci.org/SchemaPlus/schema_plus_compatibility.svg)](http://travis-ci.org/SchemaPlus/schema_plus_compatibility)
[![Coverage Status](https://img.shields.io/coveralls/SchemaPlus/schema_plus_compatibility.svg)](https://coveralls.io/r/SchemaPlus/schema_plus_compatibility)
[![Dependency Status](https://gemnasium.com/lomba/schema_plus_compatibility.svg)](https://gemnasium.com/SchemaPlus/schema_plus_compatibility)

# SchemaPlus::Compatibility

SchemaPlus::Compatibility provides compatibility support for developing and testing using different versions of ActiveRecord.

SchemaPlus::Compatibility is part of the [SchemaPlus](https://github.com/SchemaPlus/) family of Ruby on Rails ActiveRecord extension gems.

## Installation

<!-- SCHEMA_DEV: TEMPLATE INSTALLATION - begin -->
<!-- These lines are auto-inserted from a schema_dev template -->
As usual:

```ruby
gem "schema_plus_compatibility"                # in a Gemfile
gem.add_dependency "schema_plus_compatibility" # in a .gemspec
```

<!-- SCHEMA_DEV: TEMPLATE INSTALLATION - end -->

## Usage

SchemaPlus::Compatibility provides the following new methods:

* `connection.tables_without_deprecation`

  In AR 5.0, `connection.tables` is deprecated for some db adapters, and as in AR 4.2 it may actually returns views (if any are defined) as well. This method suppresses the deprecation, and continues to be ill-defined as to whether it returns tables as well as views.

* `Migration.latest`

  In AR 5.0, `ActiveRecord::Migration` is versioned using `[]`; in AR 4.2 it's not versioned.  This method returns the latest migration version in both AR 4.2 and AR 5.0

Note that the methods provided by SchemaPlus::Compatibility are subject to arbitrary change if/when SchemaPlus supports new versions of AR and/or drops support for old versions.  But SchemaPlus::Compatibility will of course follow semantic versioning.

## Compatibility

SchemaPlus::Compatibility is tested on:

<!-- SCHEMA_DEV: MATRIX - begin -->
<!-- These lines are auto-generated by schema_dev based on schema_dev.yml -->
* ruby **2.3.1** with activerecord **4.2**, using **mysql2**, **sqlite3** or **postgresql**
* ruby **2.3.1** with activerecord **5.0**, using **mysql2**, **sqlite3** or **postgresql**

<!-- SCHEMA_DEV: MATRIX - end -->

## History

* 0.1.0 - Initial release

## Development & Testing

Are you interested in contributing to SchemaPlus::Compatibility?  Thanks!  Please follow
the standard protocol: fork, feature branch, develop, push, and issue pull
request.

Some things to know about to help you develop and test:

<!-- SCHEMA_DEV: TEMPLATE USES SCHEMA_DEV - begin -->
<!-- These lines are auto-inserted from a schema_dev template -->
* **schema_dev**:  SchemaPlus::Compatibility uses [schema_dev](https://github.com/SchemaPlus/schema_dev) to
  facilitate running rspec tests on the matrix of ruby, activerecord, and database
  versions that the gem supports, both locally and on
  [travis-ci](http://travis-ci.org/SchemaPlus/schema_plus_compatibility)

  To to run rspec locally on the full matrix, do:

        $ schema_dev bundle install
        $ schema_dev rspec

  You can also run on just one configuration at a time;  For info, see `schema_dev --help` or the [schema_dev](https://github.com/SchemaPlus/schema_dev) README.

  The matrix of configurations is specified in `schema_dev.yml` in
  the project root.


<!-- SCHEMA_DEV: TEMPLATE USES SCHEMA_DEV - end -->

<!-- SCHEMA_DEV: TEMPLATE USES SCHEMA_MONKEY - begin -->
<!-- These lines are auto-inserted from a schema_dev template -->
* **schema_monkey**: SchemaPlus::Compatibility is implemented as a
  [schema_monkey](https://github.com/SchemaPlus/schema_monkey) client,
  using [schema_monkey](https://github.com/SchemaPlus/schema_monkey)'s
  convention-based protocols for extending ActiveRecord and using middleware stacks.

<!-- SCHEMA_DEV: TEMPLATE USES SCHEMA_MONKEY - end -->
