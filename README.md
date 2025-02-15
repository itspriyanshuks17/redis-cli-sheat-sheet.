# Redis CLI Cheatsheet🚀

This cheatsheet covers **all possible Redis commands** for **Strings, Lists, Sets, Hashes, and Sorted Sets**, along with their **Java (Jedis) and Python (redis-py)** implementations.

---
## 📌 1. Strings

| Command | Description |
|---------|-------------|
| `SET key value` | Set a key with a value |
| `GET key` | Get the value of a key |
| `DEL key` | Delete a key |
| `EXISTS key` | Check if a key exists |
| `APPEND key value` | Append value to a key |
| `INCR key` | Increment a key's value by 1 |
| `DECR key` | Decrement a key's value by 1 |
| `INCRBY key increment` | Increment a key's value by a given number |
| `DECRBY key decrement` | Decrement a key's value by a given number |
| `MSET key1 value1 key2 value2` | Set multiple keys at once |
| `MGET key1 key2` | Get multiple keys at once |
| `GETRANGE key start end` | Get a substring of a value |
| `SETRANGE key offset value` | Overwrite a part of a string |
| `STRLEN key` | Get length of a string |

**Java (Jedis)**:
```java
Jedis jedis = new Jedis("localhost", 6379);
jedis.set("name", "Priyanshu");
System.out.println(jedis.get("name"));
```

**Python (redis-py)**:
```python
import redis
r = redis.Redis(host='localhost', port=6379, decode_responses=True)
r.set('name', 'Priyanshu')
print(r.get('name'))
```

---
## 📌 2. Lists

| Command | Description |
|---------|-------------|
| `LPUSH key value` | Insert value at the start |
| `RPUSH key value` | Insert value at the end |
| `LPOP key` | Remove and return the first element |
| `RPOP key` | Remove and return the last element |
| `LRANGE key start stop` | Get elements from start to stop |
| `LLEN key` | Get the length of a list |
| `LINSERT key BEFORE|AFTER pivot value` | Insert value before or after another value |
| `LSET key index value` | Set a specific index in a list |
| `LTRIM key start stop` | Trim list to a given range |
| `RPOPLPUSH source destination` | Remove last element from one list and push it to another |

**Java (Jedis)**:
```java
jedis.lpush("tasks", "Task1", "Task2");
System.out.println(jedis.lrange("tasks", 0, -1));
```

**Python (redis-py)**:
```python
r.lpush('tasks', 'Task1', 'Task2')
print(r.lrange('tasks', 0, -1))
```

---
## 📌 3. Sets

| Command | Description |
|---------|-------------|
| `SADD key value` | Add value to a set |
| `SMEMBERS key` | Get all values in a set |
| `SISMEMBER key value` | Check if a value exists |
| `SREM key value` | Remove value from set |
| `SUNION key1 key2` | Get union of two sets |
| `SDIFF key1 key2` | Get difference between two sets |
| `SINTER key1 key2` | Get intersection of two sets |
| `SCARD key` | Get number of elements in a set |
| `SRANDMEMBER key [count]` | Get random element(s) from a set |

**Java (Jedis)**:
```java
jedis.sadd("students", "Alice", "Bob");
System.out.println(jedis.smembers("students"));
```

**Python (redis-py)**:
```python
r.sadd('students', 'Alice', 'Bob')
print(r.smembers('students'))
```

---
## 📌 4. Hashes

| Command | Description |
|---------|-------------|
| `HSET key field value` | Set field in a hash |
| `HGET key field` | Get field value |
| `HDEL key field` | Delete field from hash |
| `HGETALL key` | Get all fields & values |
| `HINCRBY key field increment` | Increment a hash field by value |
| `HKEYS key` | Get all field names in a hash |
| `HVALS key` | Get all values in a hash |

**Java (Jedis)**:
```java
jedis.hset("user:1", "name", "Priyanshu");
System.out.println(jedis.hgetAll("user:1"));
```

**Python (redis-py)**:
```python
r.hset('user:1', 'name', 'Priyanshu')
print(r.hgetall('user:1'))
```

---
## 📌 5. Sorted Sets

| Command | Description |
|---------|-------------|
| `ZADD key score value` | Add value with a score |
| `ZRANGE key start stop` | Get elements in range |
| `ZREM key value` | Remove value from sorted set |
| `ZRANK key value` | Get rank of value |
| `ZSCORE key value` | Get score of value |
| `ZINCRBY key increment value` | Increment score of value |
| `ZCOUNT key min max` | Count elements within score range |
| `ZREVRANGE key start stop` | Get elements in reverse order |

**Java (Jedis)**:
```java
jedis.zadd("scores", 100, "Alice");
System.out.println(jedis.zrangeWithScores("scores", 0, -1));
```

**Python (redis-py)**:
```python
r.zadd('scores', {'Alice': 100})
print(r.zrange('scores', 0, -1, withscores=True))
```

---
## 🚀 Conclusion

This cheatsheet covers **all** Redis commands with Java and Python implementations. Happy Coding! 🎯

