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

class Film < ActiveRecord::Base
  has_and_belongs_to_many :genres
end
class Genre < ActiveRecord::Base
  has_and_belongs_to_many :films
end

class Wizard < ActiveRecord::Base
  has_many :spells, :through => :spell_masteries
  has_many :spell_masteries
end
class Spell < ActiveRecord::Base
  has_many :spell_masteries
end
class SpellMastery < ActiveRecord
  belongs_to :wizard
  belongs_to :spell
end

class Beverage < ActiveRecord::Base
end
class Beer < Beverage
end
class Whisky < Beverage
end

class Barricade < ActiveRecord
  has_many :soliders, :as => :defensible
end
class Stronghold < ActiveRecord::Base
  has_many :soliders, :as => :defensible
end
class Solider < ActiveRecord
  belongs_to :defensible, :polymorphic => true
end

```

```
bundle exec rails g erd:install
bundle exec rails db:migrate

bundle install graphviz
gem 'rails-erb', group: :development
bundle exec erd

```

