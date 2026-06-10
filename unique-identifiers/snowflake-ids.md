# Snowflake IDs

Snowflake IDs are 64-bit unique identifiers developed by X/Twitter in 2010 to generate IDs across distributed systems without needing a central database. Every tweet is assigned a snowflake. 

## Format

A snowflake is composed of 64 bits:
1. The highest-order bit (MSB) is always 0
2. The next 41 bits are the timestamp - milliseconds since a custom epoch
3. The next 10 bits are the worker number - the server that generated it
4. The last 12 bits are a per-machine sequence number that resets every millisecond, which allows multiple snowflakes to be created in the same millisecond. 

Because timestamps are baked into the IDs, they are chronologically sortable without loading the actual tweets they represent. No querying databases or calling APIs necessary.

[Announcing Snowflake](https://blog.x.com/engineering/en_us/a/2010/announcing-snowflake)

[Snowflake (Archive)](https://github.com/twitter-archive/snowflake/tree/b3f6a3c6ca8e1b6847baa6ff42bf72201e2c2231)
