# redigo-ring
A simple distributed [redigo](https://github.com/garyburd/redigo) client implement with hash ring, inspired by [go-redis](https://github.com/go-redis/redis/blob/master/ring.go).

## example
```
ring := rediring.NewRing(&redix.RingOptions{
    Addrs: []string{"127.0.0.1:6379", "127.0.0.1:6380"},
})
conn := ring.Pick(key).Get()
defer conn.Close()

conn.Do("INFO")
```
