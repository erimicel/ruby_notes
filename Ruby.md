## RUBY INSTALL M1
M1 chip install early version ruby rbenv
RUBY_CFLAGS="-w" rbenv install 2.7.1

RUBY_CFLAGS="-Wno-error=implicit-function-declaration" arch -x86_64 rbenv install 2.3.7
https://github.com/rbenv/ruby-build/issues/1691

OPENSSL_CFLAGS=-Wno-error=implicit-function-declaration rbenv install 2.7.6

## RUBY: CREATE CSV FROM RAILS CONSOLE
```ruby
require 'csv'
count = Order.order(:season).group(:season).count.to_a.flatten.count
i = 0
CSV.open("orders.csv", "w") do |csv|
	while i < count-1 do 
		csv << [Order.order(:season).group(:season).count.to_a.flatten[i], Order.order(:season).group(:season).count.to_a.flatten[i+1]]
		i = i + 2
	end
end
```

