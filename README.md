This is a reporter for the [go-metrics](https://github.com/rcrowley/go-metrics)
library which will post the metrics to [Librato](https://www.librato.com/). It
was originally part of the `go-metrics` library itself, but has been split off
to make maintenance of both the core library and the client easier.

### Usage

```go
import "github.com/mihasya/go-metrics-librato"

tags := make(map[string]string)
tags["hostname"] = "myhost"
tags["service"] = "hello-world"

go librato.Librato(metrics.DefaultRegistry,
    10e9,                  // interval
    "example@example.com", // account owner email address
    "token",               // Librato API token
    tags,            	   // tags
    []float64{0.95},       // percentiles to send
    time.Millisecond,      // time unit
)
```

### About this version

This is a fork of github.com/mihasya/go-metrics-librato, trivially switching
form the Metrics API (source based) to the Measurements API (tag based).  

