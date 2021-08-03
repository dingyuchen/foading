# Shopee Entry Task Presentation

## Tools and Frameworks

### Development

- (elm) maybe
- gorilla/mux
- go-redis/redis
- go-redis/cache
- protobuf
- jwt

### Testing

- pprof for profiling
- wrk for stress testing

## API Design

SPA. 

## System Design

http - tcp - redis - mysql

## Performance

1. Without caching
2. With redis caching
- Flame graph without local cache

### Optimization
3. With local caching
- Flame graph with local cache

## Design Considerations

### JWT

Enable horizontal scaling with minimal work.

### Spa 

In line with JWT

### Protobuf

- Ease of development for marshalling and unmarshalling into structured data.
- Built-in conversion to json
- High compression on the wire

### Communication Protocol

Headers for checksum
Method byte
Size byte

Shortcomings:
- unsigned size of 255 max.

## Areas for improvement

- fasthttp
- duplexing to maximize throughput (message queue ?)
- 
