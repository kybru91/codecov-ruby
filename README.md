# Codecov Ruby Uploader

[![Codecov](https://codecov.io/github/codecov/codecov-ruby/coverage.svg?branch=master)](https://codecov.io/github/codecov/codecov-ruby?branch=master)
[![Gem Version](https://badge.fury.io/rb/codecov.svg)]
[![Build Status](https://secure.travis-ci.org/codecov/codecov-ruby.svg?branch=master)](http://travis-ci.org/codecov/codecov-ruby)
[![Anything Else]()[]

[Codecov.io](https://codecov.io/) upload support for Ruby.

## Quick Start

> Add to your `Gemfile`

```ruby
gem 'codecov', require: false, group: 'test'
```

> Add to the top of your `tests/helper.rb` file

```ruby
require 'simplecov'
SimpleCov.start

require 'codecov'
SimpleCov.formatter = SimpleCov::Formatter::Codecov
```

> In your CI Environment Variables *(not needed for [https://travis-ci.org/](https://travis-ci.org/))*

```sh
CODECOV_TOKEN="your repo token"
```
Find you repo token on your repo page at [codecov.io][1]. Repo tokens are **not** required for public repos on Travis-Ci, CircleCI, or AppVeyor CI.

## Supported CIs

| [Appveyor CI](https://www.appveyor.com/) |
| [Azure Pipelines](https://azure.microsoft.com/en-us/services/devops/pipelines/) |
| [Bitbucket Pipelines](https://bitbucket.org/product/features/pipelines) |
| [Bitrise CI](https://www.bitrise.io/) |
| [Buildkite CI](https://buildkite.com/) |
| [Circle CI](https://circleci.com/) |
| [Codeship CI](https://codeship.com/) |
| [Drone CI](https://drone.io/) |
| [GitLab CI](https://docs.gitlab.com/ee/ci/) |
| [Heroku CI](https://www.heroku.com/continuous-integration) |
| [Jenkins CI](https://www.jenkins.io/) |
| [Semaphore CI](https://semaphoreci.com/) |
| [Shippable](https://www.shippable.com/) |
| [Solano CI](https://xebialabs.com/technology/solano-ci/) |
| [TeamCity CI](https://www.jetbrains.com/teamcity/) |
| [Travis CI](https://travis-ci.org/) |
| [Wercker CI](https://devcenter.wercker.com/) |

## Configuration

## Advanced Usage

#### Submit only in CI example

```ruby
if ENV['CI'] == 'true'
  require 'codecov'
  SimpleCov.formatter = SimpleCov::Formatter::Codecov
end
```

## Useful Links

[FAQ](https://docs.codecov.io/docs/frequently-asked-questions)  
[Recipe List](https://docs.codecov.io/docs/common-recipe-list)  
[Error Reference](https://docs.codecov.io/docs/error-reference)  
[Changelog](./CHANGELOG.md)  
[Support](https://codecov.io/support)  
[Community Boards](https://community.codecov.io)  

## Caveats

1. There are known issues when `Simplecov.track_files` is enabled. We recommend that you require all code files in your tests so that Simplecov can provide Codecov with properly mapped coverage report metrics. [codecov/support#133]( https://github.com/codecov/support/issues/133)
  - https://github.com/colszowka/simplecov/blob/master/README.md#default-root-filter-and-coverage-for-things-outside-of-it

## Maintainers

- [thomasrockhu](https://github.com/thomasrockhu)

### Enterprise

For companies using Codecov Enterprise you will need to specify the following parameters.
```sh
CODECOV_URL="https://codecov.mycompany.com"
CODECOV_SLUG="owner/repo"
CODECOV_TOKEN="repository token or global token"
```
