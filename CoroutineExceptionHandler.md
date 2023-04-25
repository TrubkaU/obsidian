1. Since `CoroutineExceptionHandler` doesn't get the guarantee that it will be called in Main Thread, you have to think about it himself:
```kotlin
CoroutineExceptionHandler { _, _ ->
	// no guarantee that the code will be on UI here
	withContext(Dispatchers.Main) {
		// do here...
	}
}
```
