# Problem

Installing `mysql2` gem errors on m1 Mac.

# Solution

Make sure `mysql`, `openssl` and `zstd` are installed on Mac via Homebrew.

```
brew install mysql openssl zstd
```

Install `mysql2` gem.

```
gem install mysql2 -v '0.5.3' -- --with-mysql-config=$(brew --prefix mysql)/bin/mysql_config --with-ldflags="-L$(brew --prefix zstd)/lib -L$(brew --prefix openssl)/lib" --with-cppflags=-I$(brew --prefix openssl)/include
```
