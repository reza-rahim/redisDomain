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
