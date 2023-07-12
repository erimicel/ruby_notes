# Problem

Installing `mysql2` gem errors on m1 Mac.

# Solution

Make sure `mysql`, `openssl` are installed on Mac via Homebrew.

```
brew install mysql openssl zstd
```

Install `mysql2` gem.

```
gem install mysql2 -v '0.5.3' -- --with-mysql-config=$(brew --prefix mysql)/bin/mysql_config --with-ldflags="-L$(brew --prefix zstd)/lib -L$(brew --prefix openssl)/lib" --with-cppflags=-I$(brew --prefix openssl)/include
```

`gem install mysql2 -v 0.5.5 -- --with-ldflags=\"-L/usr/local/opt/openssl@3/lib\"`
With exact path

If root password forgotten:
`mysql.server stop`
Then, start MySQL server in safe mode
`mysql.server start --skip-grant-tables --skip-networking`
`mysql -u root`
`FLUSH PRIVILEGES;`
`UPDATE mysql.user SET authentication_string=null WHERE User='root';`
`FLUSH PRIVILEGES;`
`exit;`

`mysql -u root`
`ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'yourpasswd';`
