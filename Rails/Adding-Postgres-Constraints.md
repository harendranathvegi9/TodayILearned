# Adding Postgres Constrains

Add new migration
```
bundle exec rails g migration add-email-constraint-to-users
```

Write migration script
```
class AddEmailConstraintToUsers < ActiveRecord::Migration[5.0]
  def up
    execute %{
      ALTER TABLE
        users
      ADD CONSTRAINT
        email_must_be_sample_dot_com
      CHECK ( email ~* '^[^@]+@sample\\.com')
    }
  end
  def down
    execute %{
      ALTER TABLE
        users
      DROP CONSTRAINT
        email_must_be_sample_dot_com
    }
  end
end
```

Run migration rake
```
bundle exec rake db:migrate
```
