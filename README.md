#### CLI Queries

Here is a short list of some basic data extraction commands:

    +--------------------------------------+--------------------------------------+
    | Type                                 | Syntax and Explanation               |
    +======================================+======================================+
    | Tracing                              | Watch current live commands. Use     |
    |                                      | this with care on production. Cancel |
    |                                      | with Ctrl-C.                         |
    |                                      |     monitor                          |
    +--------------------------------------+--------------------------------------+
    | Slow Queries                         |     slowlog get 25      # print top  |
    |                                      | 25 slow queries                      |
    |                                      |     slowlog len                      |
    |                                      |     slowlog reset                    |
    +--------------------------------------+--------------------------------------+
    | Search Keys                          |     keys pattern        # Find key m |
    |                                      | atching exactly                      |
    |                                      |     keys pattern*       # Find keys  |
    |                                      | matching in back                     |
    |                                      |     keys *pattern*      # Find keys  |
    |                                      | matching somewhere                   |
    |                                      |     keys pattern*       # Find keys  |
    |                                      | matching in front                    |
    |                                      |                                      |
    |                                      | On production servers use "KEYS"     |
    |                                      | with care as it causes a full scan   |
    |                                      | of all keys!                         |
    +--------------------------------------+--------------------------------------+
    | Generic                              |     del <key>                        |
    |                                      |     dump <key>       # Serialize key |
    |                                      |     exists <key>                     |
    |                                      |     expire <key> <seconds>           |
    +--------------------------------------+--------------------------------------+
    | Scalars                              |     get <key>                        |
    |                                      |     set <key> <value>                |
    |                                      |     setnx <key> <value>   # Set key  |
    |                                      | value only if key does not exist     |
    |                                      |                                      |
    |                                      | Batch commands:                      |
    |                                      |     mget <key> <key> ...             |
    |                                      |     mset <key> <value> <key> <value> |
    |                                      |  ...                                 |
    |                                      |                                      |
    |                                      | Counter commands:                    |
    |                                      |     incr <key>                       |
    |                                      |     decr <key>                       |
    +--------------------------------------+--------------------------------------+
    | Lists                                |     lrange <key> <start> <stop>      |
    |                                      |     lrange mylist 0 -1      # Get al |
    |                                      | l of a list                          |
    |                                      |     lindex mylist 5         # Get by |
    |                                      |  index                               |
    |                                      |     llen mylist         # Get length |
    |                                      |                                      |
    |                                      |     lpush mylist "value"             |
    |                                      |     lpush mylist 5                   |
    |                                      |     rpush mylist "value"             |
    |                                      |                                      |
    |                                      |     lpushx mylist 6         # Only p |
    |                                      | ush in mylist exists                 |
    |                                      |     rpushx mylist 0                  |
    |                                      |                                      |
    |                                      |     lpop mylist                      |
    |                                      |     rpop mylist                      |
    |                                      |                                      |
    |                                      |     lrem mylist 1 "value"       # Re |
    |                                      | move 'value' count times             |
    |                                      |     lset mylist 2 6         # mylist |
    |                                      | [2] = 6                              |
    |                                      |     ltrim <key> <start> <stop>       |
    +--------------------------------------+--------------------------------------+
    | Hashes                               |     hexists myhash field1       # Ch |
    |                                      | eck if hash key exists               |
    |                                      |                                      |
    |                                      |     hget myhash field1               |
    |                                      |     hdel myhash field2               |
    |                                      |     hset myhash field1 "value"       |
    |                                      |     hsetnx myhash field1 "value"     |
    |                                      |                                      |
    |                                      |     hgetall myhash                   |
    |                                      |     hkeys myhash                     |
    |                                      |     hlen myhash                      |
    |                                      |                                      |
    |                                      | Batch commands:                      |
    |                                      |     hmget <key> <key> ...            |
    |                                      |     hmset <key> <value> <key> <value |
    |                                      | > ...                                |
    |                                      |                                      |
    |                                      | Counter commands                     |
    |                                      |     hincrby myhash field1 1          |
    |                                      |     hincrby myhash field1 5          |
    |                                      |     hincrby myhash field1 -1         |
    |                                      |                                      |
    |                                      |     hincrbrfloat myhash field2 1.123 |
    |                                      | 445                                  |
    +--------------------------------------+--------------------------------------+
    | Sets                                 | FIXME                                |
    +--------------------------------------+--------------------------------------+
    | Sorted Sets                          | FIXME                                |
    +--------------------------------------+--------------------------------------+
