# redis-go-test

参考記事  
https://qiita.com/wind-up-bird/items/f2d41d08e86789322c71

# 動作確認
```shell
redis-cli
127.0.0.1:6379> ping
PONG
```

# cache
```shell
redis-cli
127.0.0.1:6379> set test "Hello World"
OK
127.0.0.1:6379> get test
"Hello World"
127.0.0.1:6379>
```

# pub-sub
```shell
redis-cli
# 端末1
127.0.0.1:6379> subscribe test-channel
Reading messages... (press Ctrl-C to quit)
1) "subscribe"
2) "test-channel"
3) (integer) 1

# 端末2
127.0.0.1:6379> publish test-channel "Hello pub-sub"
(integer) 1

# 端末1
1) "message"
2) "test-channel"
3) "Hello pub-sub"

```

