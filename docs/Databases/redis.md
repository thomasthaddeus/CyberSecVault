# Redis Cheatsheet

## Connecting to Redis

- **Starting Redis server**: `redis-server`
- **Starting Redis CLI**: `redis-cli`

## Basic Commands

1. **SET & GET**:
   - **Purpose**: Set and retrieve a value for a given key.
   - **Usage**:

     ```bash
     SET key value
     GET key
     ```

2. **DEL**:
   - **Purpose**: Delete a key.
   - **Usage**: `DEL key`

3. **EXISTS**:
   - **Purpose**: Check if a key exists.
   - **Usage**: `EXISTS key`

4. **EXPIRE & TTL**:
   - **Purpose**: Set an expiration time on a key and check time left for expiration.
   - **Usage**:

     ```bash
     EXPIRE key seconds
     TTL key
     ```

5. **KEYS**:
   - **Purpose**: Find keys matching a pattern.
   - **Usage**: `KEYS pattern`

6. **INCR & DECR**:
   - **Purpose**: Increment and decrement the integer value of a key.
   - **Usage**:

     ```bash
     INCR key
     DECR key
     ```

## List Commands

1. **LPUSH & RPUSH**:
   - **Purpose**: Insert an element at the beginning or end of a list.
   - **Usage**:

     ```bash
     LPUSH key value
     RPUSH key value
     ```

2. **LPOP & RPOP**:
   - **Purpose**: Remove and get the first or last element from a list.
   - **Usage**:

     ```bash
     LPOP key
     RPOP key
     ```

3. **LRANGE**:
   - **Purpose**: Get a range of elements from a list.
   - **Usage**: `LRANGE key start stop`

## Set Commands

1. **SADD**:
   - **Purpose**: Add one or more members to a set.
   - **Usage**: `SADD key member [member ...]`

2. **SMEMBERS**:
   - **Purpose**: Get all members in a set.
   - **Usage**: `SMEMBERS key`

3. **SISMEMBER**:
   - **Purpose**: Check if a member is in a set.
   - **Usage**: `SISMEMBER key member`

## Hash Commands

1. **HSET & HGET**:
   - **Purpose**: Set and retrieve a field's value in a hash.
   - **Usage**:

     ```bash
     HSET key field value
     HGET key field
     ```

2. **HMSET & HMGET**:
   - **Purpose**: Set and retrieve multiple fields' values in a hash.
   - **Usage**:

     ```bash
     HMSET key field1 value1 [field2 value2 ...]
     HMGET key field1 [field2 ...]
     ```

3. **HDEL**:
   - **Purpose**: Delete one or more fields from a hash.
   - **Usage**: `HDEL key field [field ...]`

## Sorted Set Commands

1. **ZADD**:
   - **Purpose**: Add one or more members to a sorted set with scores.
   - **Usage**: `ZADD key score member [score member ...]`

2. **ZRANGE**:
   - **Purpose**: Get a range of members from a sorted set.
   - **Usage**: `ZRANGE key start stop [WITHSCORES]`

3. **ZREM**:
   - **Purpose**: Remove one or more members from a sorted set.
   - **Usage**: `ZREM key member [member ...]`

## Basic Data Types in Redis

1. **Strings**: Redis strings are binary safe and can contain any kind of data. The maximum length of a string is 512 MB.

2. **Lists**: Redis Lists are collections of string elements sorted according to the order they are inserted. They can be used as stacks or queues.

3. **Sets**: Redis Sets are unordered collections of unique strings.

4. **Hashes**: Redis Hashes are maps between string fields and string values.

5. **Sorted Sets**: In Redis Sorted Sets, every member of a set is associated with a score, allowing them to be sorted from the smallest to the largest score.

## Extended Commands

### Strings

- **APPEND**: Append a value to a key.

  ```bash
  APPEND key value
  ```

- **STRLEN**: Get the length of the value stored in a key.

  ```bash
  STRLEN key
  ```

### Lists

- **LLEN**: Get the length of a list.

  ```bash
  LLEN key
  ```

- **LINDEX**: Get an element from a list by its index.

  ```bash
  LINDEX key index
  ```

- **LTRIM**: Trim a list to the specified range.

  ```bash
  LTRIM key start stop
  ```

### Sets

- **SCARD**: Get the number of members in a set.

  ```bash
  SCARD key
  ```

- **SREM**: Remove one or more members from a set.

  ```bash
  SREM key member [member ...]
  ```

### Hashes

- **HLEN**: Get the number of fields in a hash.

  ```bash
  HLEN key
  ```

- **HKEYS**: Get all the fields in a hash.

  ```bash
  HKEYS key
  ```

- **HVALS**: Get all the values in a hash.

  ```bash
  HVALS key
  ```

- **HINCRBY**: Increment the integer value of a hash field by the given number.

  ```bash
  HINCRBY key field increment
  ```

### Sorted Sets

- **ZCARD**: Get the number of members in a sorted set.

  ```bash
  ZCARD key
  ```

- **ZSCORE**: Get the score associated with the given member in a sorted set.

  ```bash
  ZSCORE key member
  ```

- **ZRANK**: Determine the index of a member in a sorted set.

  ```bash
  ZRANK key member
  ```

## Transactions

Redis supports basic transactions using the following commands:

- **MULTI**: Marks the start of a transaction block.
- **EXEC**: Executes all commands issued after MULTI.
- **DISCARD**: Discards all commands issued after MULTI.
- **WATCH**: Watches a key for modifications.

## Pub/Sub

Redis Pub/Sub provides a way to send messages between clients:

- **SUBSCRIBE**: Listen for messages sent to the specified channels.
- **PUBLISH**: Post a message to a channel.
- **UNSUBSCRIBE**: Stop listening to messages from the specified channels.

## Persistence

Redis offers options for durability and data persistence:

- **SAVE**: Create a snapshot of the dataset.
- **BGSAVE**: Create a snapshot of the dataset in the background.
- **AOF**: Append Only File mode logs every write operation to a file.

## Administration

- **INFO**: Get information and statistics about the server.
- **CONFIG**: Get or set configuration parameters.
- **SLAVEOF**: Make the server a replica/slave of another instance.

## Advanced Data Structures

### Bitmaps

Bitmaps are not a separate data type, but are operations on strings that treat them as arrays of bits. Useful for analytics and sets with huge cardinalities.

- **SETBIT**: Set or clear the bit at offset in the string value stored at key.

  ```bash
  SETBIT key offset value
  ```

- **GETBIT**: Returns the bit value at offset in the string value stored at key.

  ```bash
  GETBIT key offset
  ```

- **BITCOUNT**: Count set bits in a string.

  ```bash
  BITCOUNT key [start end]
  ```

### HyperLogLogs

HyperLogLogs are a probabilistic data structure that can estimate the cardinality of a set.

- **PFADD**: Add values to a HyperLogLog.

  ```bash
  PFADD key element [element ...]
  ```

- **PFCOUNT**: Count the approximate number of unique values.

  ```bash
  PFCOUNT key [key ...]
  ```

- **PFMERGE**: Merge multiple HyperLogLogs into a single one.

  ```bash
  PFMERGE destkey sourcekey [sourcekey ...]
  ```

## Geospatial Indexes

Redis supports geospatial indexes with the `GEO` commands, which allow for querying by radius, distance calculations, and more.

- **GEOADD**: Add one or more geospatial items.

  ```bash
  GEOADD key longitude latitude member [longitude latitude member ...]
  ```

- **GEODIST**: Get the distance between two members.

  ```bash
  GEODIST key member1 member2 [unit]
  ```

- **GEOHASH**: Get the Geohash string representation of a position.

  ```bash
  GEOHASH key member [member ...]
  ```

- **GEOPOS**: Get the position (longitude, latitude) of one or more members.

  ```bash
  GEOPOS key member [member ...]
  ```

- **GEORADIUS**: Query members within a given distance from a point.

  ```bash
  GEORADIUS key longitude latitude radius m|km|ft|mi [WITHCOORD] [WITHDIST] [WITHHASH]
  ```

## Streams

Redis Streams is a log-like data structure for storing multiple fields and string values with an automatic, server-assigned timestamp.

- **XADD**: Appends a new entry.

  ```bash
  XADD key ID field value [field value ...]
  ```

- **XRANGE**: Returns entries within a range.

  ```bash
  XRANGE key start end [COUNT count]
  ```

- **XREAD**: Read data from streams.

  ```bash
  XREAD [COUNT count] [BLOCK milliseconds] STREAMS key [key ...] ID [ID ...]
  ```

### Cluster Commands

Redis supports horizontal partitioning across multiple servers with clustering.

- **CLUSTER ADDSLOTS**: Assign slots to the current node.
- **CLUSTER INFO**: Provides information about the cluster.
- **CLUSTER MEET**: Force a node to handshake with another.

### Security

- **AUTH**: Authenticate to the server.

  ```bash
  AUTH password
  ```

- **ACL LOAD**: Reload the ACLs from the configured `aclfile`.
- **ACL LIST**: List the current ACL rules in ACL config format.

### Scripting

Redis supports Lua scripting.

- **EVAL**: Executes a Lua script.

  ```bash
  EVAL script numkeys key [key ...] arg [arg ...]
  ```

- **EVALSHA**: Executes a Lua script cached on the server.

  ```bash
  EVALSHA sha1 numkeys key [key ...] arg [arg ...]
  ```

- **SCRIPT LOAD**: Load a script into the scripts cache, without executing it.

  ```bash
  SCRIPT LOAD script
  ```
