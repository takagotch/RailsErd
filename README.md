### RailsErd
---

https://github.com/voormedia/rails-erd


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
```

```
bundle exec rails g erd:install
bundle exec rails db:migrate

bundle install graphviz
gem 'rails-erb', group: :development
bundle exec erd

```

