## Domain

```bash
HMSET jane1 name jane email jane@redis.com password password

HGET jane1 name

HGETALL jane1
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

ZREVRANGE all-orders:{jane1} 0 0
```

```bash
HMSET order:{jane1}:1566942593 user jane1 orderNumber 1566942593 name jane address address totalQty 3 price 200

HMSET order:{jane1}:1566942594 user jane1 orderNumber 1566942594 name jane address address totalQty 2 price 250

ZADD all-orders:{jane1} 1566942593 order:{jane1}:1566942593 

ZADD all-orders:{jane1} 1566942594 order:{jane1}:1566942594

ZREVRANGE all-orders:{jane1} 0 1
```

```bash
HMSET lineItem:{jane1}:1566942593:1  product brad totalQty 1 price 10

HMSET lineItem:{jane1}:1566942593:2  product hohn totalQty 2 price 20

SADD all-lineItem:{jane1}:1566942593  order:{jane1}:1566942593:1

SADD all-lineItem:{jane1}:1566942593 order:{jane1}:1566942593:2
```

```bash
ZREVRANGE all-orders:{jane1} 0 0

SMEMBERS all-lineItem:{jane1}:1566942593
```
