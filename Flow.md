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

It's possible to collect state with lifecycle:
```kotlin
val state = flow {

}.stateIn(
	viewModelScope, 
	SharingState.WhileSubscribed(5000l)
)

val state by viewModel.state.collectAsStateWithLifeCycle() 
```

Since if you will navigate to the next screen the previous one will take the events from the flow since the viewModelScop is active.