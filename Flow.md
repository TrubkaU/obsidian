There are types of flow:
1. Regular flow:
```kotlin

flow {

}
```

2. StateFlow
3. SharedFlow

StateFlow and SharedFlow are hot flows. Regular flow is cold.

SharedFlow can emmit the same value multiple times. Good to use for navigation, send single events.
StateFlow to keep the state for Compose UI.

StateFlow must have the default init value, SharedFlow not.