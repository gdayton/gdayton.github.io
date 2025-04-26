Generate the Gemfile:
```
bundle init
```

Add the following to the Gemfile:
```
gem "jekyll", "3.3.0"
gem 'github-pages', group: :jekyll_plugins #comment this line out to avoid github auth errors
```

# To update website run this:

Run these commands:
```
bundle install
bundle exec jekyll build
```

To run jekyll page locally:
```
bundle exec jekyll serve
```