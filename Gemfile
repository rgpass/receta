source 'https://rubygems.org'

gem 'rails', '4.0.3'
gem 'pg'
gem 'sass', '3.2.19' # Need specific version due to sass/sprockets issue
gem 'sass-rails', '~> 4.0.0'
gem 'uglifier', '>= 1.3.0'
gem 'coffee-rails', '~> 4.0.0'
gem 'jquery-rails'
# gem 'turbolinks' # Removed since it's not applicable for Angular apps
gem 'jbuilder', '~> 1.2'
gem 'bower-rails' # Connects Rails to Bower for front-end dependency mgmt
gem 'angular-rails-templates' # Solves CORS and asset pipeline issues: http://angular-rails.com/find_and_browse.html


# Mostly Heroku-specific gems, don't hurt to keep if not using Heroku
gem 'foreman'
group :production, :staging do
  gem "rails_12factor"
  gem "rails_stdout_logging"
  gem "rails_serve_static_assets"
end

group :doc do
  gem 'sdoc', require: false
end

group :development, :test do
  gem 'rspec'
  gem 'rspec-rails', '~> 2.0'
  gem 'factory_girl_rails', '~> 4.0'
  gem 'capybara'
  gem 'database_cleaner'
  gem 'selenium-webdriver'
end
