## RUBY INSTALL M1
M1 chip install early version ruby rbenv
RUBY_CFLAGS="-w" rbenv install 2.7.1

RUBY_CFLAGS="-Wno-error=implicit-function-declaration" arch -x86_64 rbenv install 2.3.7
https://github.com/rbenv/ruby-build/issues/1691

OPENSSL_CFLAGS=-Wno-error=implicit-function-declaration rbenv install 2.7.6
