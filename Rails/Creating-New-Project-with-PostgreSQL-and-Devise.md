# Creating new project with PostgreSQL and Devise

## Creating new Project and Setup Database
Creating the project
```
rails new --skip-turbolinks --skip-spring -d postgresql projectname
```

Navigate to project directory
``` 
cd projectname
```

Ceate new PostgreSQL user via command line
```
createuser --createdb --login -P newusername
```

Connect to PostgreSQL with host parameter
``` 
psql -h '/directory/postgresql' -d postgres
```

Creating new user using SQL command
```
CREATE USER newusername PASSWORD 'password';
```

Creating new user with creating database permission
``` 
CREATE USER newusername WITH LOGIN NOSUPERUSER INHERIT CREATEDB NOCREATEROLE NOREPLICATION;
```

Setup database
``` 
bundle exec rake db:create
bundle exec rake db:migrate
```

Start server with port parameter
```
bundle exec rails server -p 8080
```

## Install Devise 
Adding new gem to Gemfile
```
gem 'devise'
```

Run the command
``` 
bundle install
```

Generate Devise config
```
bundle exec rails generate devise:install
```

Generat Devise user model and database table
``` 
bundle exec rails generate devise user
```

Run database migrate
``` 
bundle exec rake db:migrate
```

Add devise's filter to ApplicationController
``` 
before_action :authenticate_user!
```

Restart server

## Install Bower
Install Bower
``` 
sudo npm install -g bower
```

Adding new gem to Gemfile
``` 
gem 'bower-rails'
```

Run command
``` 
bundle install
``` 

Run the rake
``` 
bundle exec rake -T bower
```

Adding Bowerfile and input this line
``` 
asset 'bootstrap-sass-official'
```

Run bower rake to install libraries
``` 
bundle exec rake bower:install
```

Adding this line to application.css
```
*= require 'bootstrap-sass-official'
```

Restart rails server 

## Generate Devise views
``` 
bundle exec rails generate devise:views
```

## Notes: 
Kill server process when it still alive
```
kill -9 PID 2182
```