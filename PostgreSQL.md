## Install pg with app
gem install pg -- --with-pg-config=/Applications/Postgres.app/Contents/Versions/14/bin/pg_config

## Restore pg
pg_restore -h localhost -d database ./tmp/dump.dump

### SQL: SHOW TABLE SIZES POSTGRESQL
```sql
SELECT nspname || '.' || relname AS "relation",
    pg_size_pretty(pg_total_relation_size(C.oid)) AS "total_size"
  FROM pg_class C
  LEFT JOIN pg_namespace N ON (N.oid = C.relnamespace)
  WHERE nspname NOT IN ('pg_catalog', 'information_schema')
    AND C.relkind <> 'i'
    AND nspname !~ '^pg_toast'
  ORDER BY pg_total_relation_size(C.oid) DESC;
```

### Relations
<img width="541" alt="Screenshot 2023-06-12 at 00 50 13" src="https://github.com/erimicel/tech_notes/assets/17678162/0f4016cd-c896-49db-a247-976aee9c9e45">
