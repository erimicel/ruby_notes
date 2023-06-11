## Install pg with app
gem install pg -- --with-pg-config=/Applications/Postgres.app/Contents/Versions/14/bin/pg_config

## Restore pg
pg_restore -h localhost -d database ./tmp/dump.dump
