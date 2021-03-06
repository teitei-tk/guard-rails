# Guard-rails is watching on your railses!

[![Gem Version](https://badge.fury.io/rb/guard-rails.svg)](http://badge.fury.io/rb/guard-rails)
[![Build Status](https://travis-ci.org/ranmocy/guard-rails.svg)](https://travis-ci.org/ranmocy/guard-rails)
[![Dependency Status](https://gemnasium.com/ranmocy/guard-rails.svg)](https://gemnasium.com/ranmocy/guard-rails)
[![Code Climate](https://codeclimate.com/github/ranmocy/guard-rails.svg)](https://codeclimate.com/github/ranmocy/guard-rails)
[![Test Coverage](https://codeclimate.com/github/ranmocy/guard-rails/badges/coverage.svg)](https://codeclimate.com/github/ranmocy/guard-rails)

## Main repository
Currently, the official fork repository is at [ranmocy/guard-rails][ranmocy-guard-rails].
Please, come here and communicate with me.

## Install

Please make sure to have [Guard][guard] installed before continuing.

Add Guard::Rails to your `Gemfile`:

```ruby
group :development do
  gem 'guard-rails', require: false
end
```

Add the default Guard::Rails template to your `Guardfile` by running:

```bash
$ guard init rails
```

Add options in Guardfile
```rb
guard :rails, port: 3000, host: '0.0.0.0' do
  watch('Gemfile.lock')
  watch(%r{^(config|lib)/.*})
end
```

Now I can automatically restart your Rails development server as your files change!

## Lots of fun options growing!

* `:daemon` runs the server as a daemon, without any output to the terminal that started `guard` (**default `false`**)
* `:debugger` enable the debugger in server. Requires ruby-debug gem. (**default `false`**)
* `:environment` is the server environment (**default `development`**)
* `:force_run` kills any process that's holding the listen port before attempting to (re)start Rails (**default `false`**)
* `:pid_file` specify your pid\_file (**default `tmp/pids/[RAILS_ENV].pid`**)
* `:host` is where the server is hosted (**default `localhost`**)
* `:port` is the server port number (**default `3000`**)
* `:root` lets you specify the Rails root, i.e. for using guard-rails to run a dummy app within an engine (try `:root => '/spec/dummy'`).
* `:server` the webserver engine to use (**try `:server => :thin`**)
* `:start_on_start` will start the server when starting Guard (**default `true`**)
* `:timeout` waits when restarting the Rails server, in seconds (**default `30`**).
* `:zeus_plan` the [custom plan][zeus-custom-plan] in zeus, only works when `zeus` option is `true` (**default `server`**)
* `:zeus` support [zeus][zeus] to boost rails init speed (**default `false`**).
* `:CLI` construct the runner command as you will! Will omit all options above except `pid_file`! (**default `rails server --pid tmp/pids/[RAILS_ENV].pid`**)

## How-to

* **Multiple instances** use `pid_file` option to run multiple instances with same rails\_env.
* **Avoid multiple autoruns when editing by VIM and Emacs** move the backup files to somewhere else or just ignore them in Guardfile.
* **Use binding.pry in Rails** Actually you can't! See discussion [here](https://github.com/ranmocy/guard-rails/issues/24).

## Philosophy

* **All Platforms** MRI is the main test case. But will be tested under REE and JRuby.
* **Live on the edge** Guard-Rails will be tested under Ruby 2.2.3 to 2.3.0 with newest gems.
* [Semantic Version](http://semver.org/)

## Contribute

The best way to contact me is the Issues and Pull Request system on GitHub.
Currently the official fork repository is at [ranmocy/guard-rails][ranmocy-guard-rails].

Please, post your issues or pull requests there.
And I will be there as your call.

## Contributors

* Ranmocy Sheng
* John Bintz
* cablegram
* Joel Moss
* Sidney Burks
* Paul Schyska
* Adam Michel
* Adib Saad
* Cezary Baginski
* Nathan Broadbent
* Tim Preston
* killphi
* Michael
* Benjamin Sullivan
* Johnny Robeson
* Peter Ragone
* Grant Hutchins and Jonathan Mukai-Heidt
* Everard Brown
* Sho Kusano
* Darrin Holst
* Leo Lou
* Luciano Sousa
* Michel Pavan Macedo

## Copyright

Guard-rails is under **[MIT license][MIT]**.

[ranmocy-guard-rails]: http://github.com/ranmocy/guard-rails
[guard]: https://github.com/guard/guard
[zeus]: https://github.com/burke/zeus
[zeus-custom-plan]: https://github.com/burke/zeus/blob/master/docs/ruby/modifying.md
[MIT]: http://opensource.org/licenses/MIT
