# README

installfest.railsbridge.org tutorial on deploying to heroku. Worked just fine from my Ubunto laptop, but I'm tyring to get my Ubuntu on Windows IDE running as well, and apparently it's hit a snag. I'm pushing the repo here so I can figure out what went wrong later.

Things you may want to cover:

* Ruby version: 2.3.3.p222

The problem is with the Gemfile. It throws an error stating the need for sqlite3, but heroku doesn't use sqlite3. I think the tutorial had me replace that gem with some kind of false positive?

It had me change this:

gem 'sqlite3'

to this:

group :development, :test do
  gem 'sqlite3'
end

group :production do
  gem 'pg'
end
