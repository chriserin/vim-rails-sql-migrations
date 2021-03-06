# rails-sql-migrations.vim

> rails.vim helper for generating SQL migrations for Rails projects

I built this for all my friends at [Hashrocket](https://hashrocket.com/) so
that they never again have to manually type out the `up` and `down` methods
with their respective heredocs.

This plugin requires and works with the
[`rails.vim`](https://github.com/tpope/vim-rails) plugin to provide a set of
file commands for creating and opening SQL migrations.

It works just like the `:Emigration` helper, but, when used to create a new
migration, generates a SQL-based migration.

```
:Esql create_posts_table!
```

which generates and opens:

```ruby
# db/migrate/20161016190650_create_posts_table.rb
class CreatePostsTable < ActiveRecord::Migration
  def up
    execute <<-SQL
    SQL
  end

  def down
    execute <<-SQL
    SQL
  end
end
```

This plugin works with all the `rails.vim` commands you are used to:
`:Ssql`, `:Vsql`, etc. It also provides tab completion of your project's
existing migrations.
