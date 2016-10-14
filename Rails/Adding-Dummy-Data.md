# Adding Dummy Data
Adding new gem 
```
gem 'faker'
```

Install 
```
bundle install
```

Writing script to generate data in db/seeds.rb file
```
3_000.times do |i|
  Customer.create!(
    first_name: Faker::Name.first_name,
    last_name: Faker::Name.last_name,
    username: "#{Faker::Internet.user_name}#{i}",
    email: Faker::Internet.user_name + i.to_s + "@#{Faker::Internet.domain_name}"
  )
end
```

Run rake to insert database
```
bundle exec rake db:seed
```