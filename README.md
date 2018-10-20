### RailsErd
---

https://github.com/voormedia/rails-erd

http://voormedia.github.io/rails-erd/gallery.html

```
attributes:
  - content
  - foreign_key
  - inheritance
disconnected: true
filename: erd
filetype: pdf
indirect: true
inheritance: false
markup: true
notation: false
markup: true
notation: simple
orientation: horizontal
polymorphism: false
sort: true
warn: true
title: sample title
exclude: null
only: null
only_recursion_depth: null
prepend_primary: false
cluster: false
splines: spline
```

```ruby
ActiveRecord::Schma.define do
  create_table "" do |t|
    t.decimal :aperture
    t.binary :data, :null => false
    t.text :desciption, :limit => 512
    t.string :filename, :null => false, :limit => 64
    t.boolean :flash
    t.integer :iso
    t.float :shutter-speed
    t.datetime :taken_at, :null => false
  end
end

class Country < ActiveRecord::Base
  has_one :head_of_state
end
class HeadOfState < ActiveRecord::Base
  belongs_to :country
  validates_presence_of :country
end


class Galleon < ActiveRecord::Base
  has_many :cannons
  validates_lenght_of :cannons, :maximum => 36
end











```

```
bundle exec rails g erd:install
bundle exec rails db:migrate

bundle install graphviz
gem 'rails-erb', group: :development
bundle exec erd

```

