source "https://rubygems.org"
gemspec :name => "chef"

gem "activesupport", "< 4.0.0", :group => :compat_testing, :platform => "ruby"

gem 'chef-config', path: "chef-config"

group(:docgen) do
  gem "yard"
end

group(:maintenance) do
  gem "tomlrb"

  # To sync maintainers with github
  gem "octokit"
  gem "netrc"
end

group(:development, :test) do

  gem "simplecov"
  gem 'rack', "~> 1.5.1"

  gem 'cheffish', "~> 1.3", "!= 1.3.1"

  gem 'ruby-shadow', :platforms => :ruby unless RUBY_PLATFORM.downcase.match(/(aix|cygwin)/)

  # For external tests
  gem 'chefspec', github: 'jkeiser/chefspec', branch: 'jk/chefspec-12.5'
  gem 'chef-sugar'
  gem 'poise', github: 'poise/poise', branch: 'deeecb890a6a0bc2037dfb09ce0fd0a8931519aa'
  gem 'halite', github: 'poise/halite'
  gem 'foodcritic', github: 'acrmp/foodcritic', branch: 'v5.0.0'
  gem 'chef-rewind'
end

# If you want to load debugging tools into the bundle exec sandbox,
# add these additional dependencies into chef/Gemfile.local
eval(IO.read(__FILE__ + '.local'), binding) if File.exists?(__FILE__ + '.local')
