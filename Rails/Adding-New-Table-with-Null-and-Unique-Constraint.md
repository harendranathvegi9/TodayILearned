# Adding new Table with Null and Unique Constraint

Generate migrate script and model
```
bundle exec rails g model customer first_name:string last_name:string email:string username:string
```

Change null constraint and adding index 
```
class CreateCustomers < ActiveRecord::Migration[5.0]
  def change
    create_table :customers do |t|
      t.string :first_name, null: false
      t.string :last_name, null: false
      t.string :email, null: false
      t.string :username, null: false

      t.timestamps null: false
    end

    add_index :customers, :email, unique: true
    add_index :customers, :username, unique: true
  end
end
```

Run migrate rake
```
bundle exec rake db:migrate
```