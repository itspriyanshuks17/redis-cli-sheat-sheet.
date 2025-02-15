# Redis CLI Cheat Sheet 📌

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Basic Commands](#basic-commands)
- [Data Types & Commands](#data-types--commands)
  - [Strings](#strings)
  - [Lists](#lists)
  - [Sets](#sets)
  - [Hashes](#hashes)
  - [Sorted Sets](#sorted-sets)
  - [Keys](#keys)
  - [Transactions](#transactions)
- [Java Implementation](#java-implementation)
- [Python Implementation](#python-implementation)

---
## Introduction
Redis (Remote Dictionary Server) is an in-memory key-value data store used as a database, cache, and message broker.

## Installation
```sh
sudo apt update && sudo apt install redis-server -y
```
To check if Redis is running:
```sh
redis-cli ping
```
Expected response:
```sh
PONG
```

## Basic Commands
| Command | Description |
|---------|-------------|
| `SET key value` | Set a key with a value |
| `GET key` | Get the value of a key |
| `DEL key` | Delete a key |
| `EXISTS key` | Check if a key exists |
| `EXPIRE key seconds` | Set a time-to-live (TTL) for a key |
| `TTL key` | Get the remaining TTL of a key |
| `FLUSHALL` | Remove all keys from all databases |

---
## Data Types & Commands

### Strings
| Command | Description |
|---------|-------------|
| `SET key value` | Store a string value |
| `GET key` | Retrieve a string value |
| `INCR key` | Increment an integer value |
| `DECR key` | Decrement an integer value |
| `APPEND key value` | Append a value to a key |

### Lists
| Command | Description |
|---------|-------------|
| `LPUSH list value` | Insert a value at the beginning of a list |
| `RPUSH list value` | Insert a value at the end of a list |
| `LPOP list` | Remove the first element of a list |
| `RPOP list` | Remove the last element of a list |
| `LRANGE list start stop` | Get elements in a range |

### Sets
| Command | Description |
|---------|-------------|
| `SADD set value` | Add a value to a set |
| `SREM set value` | Remove a value from a set |
| `SMEMBERS set` | Get all values from a set |
| `SISMEMBER set value` | Check if a value exists in a set |

### Hashes
| Command | Description |
|---------|-------------|
| `HSET hash field value` | Set a field in a hash |
| `HGET hash field` | Get the value of a field in a hash |
| `HDEL hash field` | Delete a field from a hash |
| `HGETALL hash` | Get all fields and values in a hash |

### Sorted Sets
| Command | Description |
|---------|-------------|
| `ZADD zset score value` | Add a value with a score |
| `ZRANGE zset start stop` | Get values in a range |
| `ZRANK zset value` | Get the rank of a value |
| `ZREM zset value` | Remove a value from a sorted set |

### Keys
| Command | Description |
|---------|-------------|
| `KEYS pattern` | List keys matching a pattern |
| `EXPIRE key seconds` | Set a TTL on a key |
| `TTL key` | Get the remaining TTL of a key |

### Transactions
| Command | Description |
|---------|-------------|
| `MULTI` | Start a transaction |
| `EXEC` | Execute a transaction |
| `DISCARD` | Cancel a transaction |

---
## Java Implementation (Jedis)
```java
package com.example;
import redis.clients.jedis.Jedis;

public class RedisExample {
    public static void main(String[] args) {
        Jedis jedis = new Jedis("localhost", 6379);
        System.out.println("Connected to Redis!");
        
        jedis.set("name", "Priyanshu");
        System.out.println("Stored name: " + jedis.get("name"));
        
        jedis.close();
    }
}
```

---
## Python Implementation (redis-py)
Install redis-py:
```sh
pip install redis
```

Python Code:
```python
import redis

client = redis.StrictRedis(host='localhost', port=6379, decode_responses=True)
client.set("name", "Priyanshu")
print("Stored name:", client.get("name"))
```

---
### More Redis Features
- Pub/Sub messaging
- Streams
- Geospatial indexes
- HyperLogLogs

🚀 **Enjoy using Redis!** 🚀
