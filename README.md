# StopWatch
A Xojo class for measuring time.

## Usage
`StopWatch` provides an easy way to time how long events take to occur.

```xojo
Var watch As New StopWatch
watch.Start
// Do something that you want to time...
watch.Stop

// Easy access to watch properties:
Var ms As Double = watch.ElapsedMilliseconds
Var t As Double = watch.ElapsedTicks
Var di As DateInterval = watch.Elapsed

// StopWatch will even format the interval into a string:
Var s As String = watch.ElapsedAsString // E.g "4 minutes, 3 seconds, 89 ms"

// Query if the stopwatch is running:
If watch.IsRunning Then
  // Do something
End If

// You can call `ElapsedTicks`, etc whilst the stopwatch is running too.
```

## Limitations
If the stopwatch is left running for > 28 days, calling `ElapsedMilliseconds` or `ElapsedTicks` will raise an `UnsupportedOperationException`. This is because there are between 28-31 days in a month 365-366 days in a year.
