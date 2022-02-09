# Watermill otel tracable go-channel
Pass context into pubsub to CQRS handler

 - Warning: should using in single pod command. (cqrs)
 - Only work in go channel pub/sub mode.

# Install

```
go get -u "github.com/hpcslag/watermill-otel-tracable-gochannel"
```

# Setup

Setup 

``` go

import otelTraceChannel "github.com/hpcslag/watermill-otel-tracable-gochannel/gochannel"

// Important to use JSON Marshaler
cqrsMarshaler := cqrs.JSONMarshaler{}

router, err := message.NewRouter(message.RouterConfig{}, logger)
if err != nil {
    panic(err)
}
// ...

commandsChannel := otelTraceChannel.NewGoChannel(
    otelTraceChannel.Config{},
    watermill.NewStdLogger(true, true),
)

// ... 

```

# Reference

Original code please refer to watermill repository: https://github.com/ThreeDotsLabs/watermill/blob/master/pubsub/gochannel/pubsub.go
