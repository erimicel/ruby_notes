<img width="460" alt="Screenshot 2023-06-12 at 00 50 31" src="https://github.com/erimicel/tech_notes/assets/17678162/8412e43b-ae3e-4a1f-9ba6-635bae135537">

## Rails 7.0.5 New app
rails new myapp -d postgresql --css=tailwind --javascript=esbuild --skip-test --skip-jbuilder  --skip-action-text --skip-action-mailbox --skip-action-mailer --skip-active-storage

### Start server
```bash
bin/dev
```

## ActionText

# In config/application.rb
```ruby
config.action_view.sanitized_allowed_tags = ['strong', 'em', 'a']
config.action_view.sanitized_allowed_attributes = ['href', ‘id’, ‘title']
```

To allow or sanitize html attributes and tags

## Localization

### Date with l method and format => locales.yml
<%= l user.created_at, format: :short %>

## Credentials
```bash
EDITOR='code --wait' rails credentials:edit
```

## Routes
http://localhost:3000/rails/info/routes

## Database Queries

### RAILS: ORDER STRING AS INT WITH SQL
```ruby
.order('ABS(CAST(number AS int))')
```

### SQL: extract year from date with sql
```ruby
MODEL.where("extract(year  from debit_date) = ?",Date.today.year)
```

## Capistrano

### Run puma server in rvm env. on direct machine
```bash
~/.rvm/bin/rvm default do bundle exec puma -C /home/deploy/projects/app/shared/puma.rb --daemon
```

```bash
cap production puma:start
cap production puma:restart
cap production puma:stop
cap production deploy
```

## Sunspot Apache Solr

```bash
rake sunspot:solr:start
rake sunspot:solr:reindex

nohup rake sunspot:solr:reindex & (Background task)
```
