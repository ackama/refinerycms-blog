source "https://rubygems.org"

gem "refinerycms-authentication-devise", '~> 2.0'

gemspec

gem 'refinerycms', '~> 4.0'


group :development, :test do
  gem 'refinerycms-testing', '~> 4.0'
end

# Add the default visual editor, for now.
gem 'refinerycms-wymeditor', ['~> 2.0', '>= 2.0.0']

group :test do
  gem 'launchy'
  gem 'poltergeist'
  gem 'listen'
end

# Database Configuration
unless ENV['TRAVIS']
  gem 'activerecord-jdbcsqlite3-adapter', :platform => :jruby
  gem 'sqlite3', :platform => :ruby
end

if !ENV['TRAVIS'] || ENV['DB'] == 'mysql'
  gem 'activerecord-jdbcmysql-adapter', :platform => :jruby
  gem 'jdbc-mysql', '= 5.1.13', :platform => :jruby
  gem 'mysql2', :platform => :ruby
end

if !ENV['TRAVIS'] || ENV['DB'] == 'postgresql'
  gem 'activerecord-jdbcpostgresql-adapter', :platform => :jruby
  gem 'pg', :platform => :ruby
end

# Refinery/rails should pull in the proper versions of these
group :assets do
  gem 'sass-rails'
  gem 'coffee-rails'
end

# Load local gems according to Refinery developer preference.
if File.exist? local_gemfile = File.expand_path('../.gemfile', __FILE__)
  eval File.read(local_gemfile)
end
