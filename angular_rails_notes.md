* Have a different package manager for front-end assets
  * RubyGems don't exist for each front-end feature we'll need
  * RubyGems don't explicitly say which version of front-end assets they bundle
    * Ex: jquery-rails -- which version of jQuery?
  * Use bower to manage front-end dependencies
    * $ npm install bower
    * Gemfile
      * gem 'bower-rails'
    * $ rake -T bower   -- all available rake tasks for bower
    * Create Bowerfile in root, similar to Gemfile
    * rake bower:install
      * Installs files to vendor/assets/bower_components
      * This isn't the standard for Rails, so need to add it to the asset path
      * application.rb
        ```
          config.assets.paths << Rails.root.join("vendor","assets","bower_components")
          config.assets.paths << Rails.root.join("vendor","assets","bower_components","bootstrap-sass-official","assets","fonts")
          config.assets.precompile << %r(.*.(?:eot|svg|ttf|woff)$)
        ```
      * application.css --> application.css.scss
      * application.js
        * Remove turbolinks
        * Add angular/angular
          * This is required because we need to say exactly what's loaded in
            or else it'll load in random files (see bower_components/angular)

* Pre-populating cache files
  * Gemfile: gem 'angular-rails-templates'
  * Bowerfile: asset 'angular-route'
  * rake bower:install
  * application.js
    ```
      //= require angular-route/angular-route
      //= require angular-rails-templates
    ```

* Views
  * Created index.html which refers to ng-views
  * Created route in app.coffee
  * Created template in assets/javascripts/templates/index.html
