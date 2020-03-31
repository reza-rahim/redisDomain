## Domain

```bash
HMSET {redisshop:user:jane1} name jane email jane@redis.com password password

HGET redisshop:user:jane1 name

HGETALL redisshop:user:jane1
```

```bash
HMSET redisshop:product:brad key brad imagePath images/brad.jpeg description sa price 10.00

HMSET redisshop:product:john key john imagePath images/john.jpeg description sa price 15.00

HGET redisshop:product:john key

HGETALL redisshop:product:john
```

```bash
ZADD all-products 10.00 redisshop:product:brad  

ZADD all-products 15.00 redisshop:product:john 

ZREVRANGE all-products 0 0

ZREVRANGE all-products 0 1


```

```bash
HMSET order:{redisshop:user:jane1}:1566942593 user redisshop:user:jane1 orderNumber 1566942593 name jane address address totalQty 3 price 200

HMSET order:{redisshop:user:jane1}:1566942594 user redisshop:user:jane1 orderNumber 1566942594 name jane address address totalQty 2 price 250

ZADD all-orders:{redisshop:user:jane1} 1566942593 order:{redisshop:user:jane1}:1566942593 

ZADD all-orders:{redisshop:user:jane1} 1566942594 order:{redisshop:user:jane1}:1566942594

ZREVRANGE all-orders:{redisshop:user:jane1} 0 1
```

```bash
HMSET lineItem:{redisshop:user:jane1}:1566942593:1  product redisshop:product:brad totalQty 1 price 10

HMSET lineItem:{redisshop:user:jane1}:1566942593:2  product redisshop:product:john  totalQty 2 price 20

SADD all-lineItem:{redisshop:user:jane1}:1566942593  order:{redisshop:user:jane1}:1566942593:1

SADD all-lineItem:{redisshop:user:jane1}:1566942593 order:{redisshop:user:jane1}:1566942593:2
```

```bash
ZREVRANGE all-orders:{redisshop:user:jane1} 0 0

SMEMBERS all-lineItem:{redisshop:user:jane1}:1566942593
```
