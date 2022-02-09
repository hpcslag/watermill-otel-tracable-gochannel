# Watermill otel tracable go-channel
Pass context into pubsub to CQRS handler

 - Warning: should using in single pod command.
 - Only work in go channel pub/sub mode.

# Setup

Setup 

``` go

// Important to use JSON Marshaler
cqrsMarshaler := cqrs.JSONMarshaler{}

router, err := message.NewRouter(message.RouterConfig{}, logger)
if err != nil {
    panic(err)
}
// ...

commandsChannel := otelTraceChannel.NewGoChannel(
    gochannel.Config{},
    watermill.NewStdLogger(true, true),
)

// ... 

```