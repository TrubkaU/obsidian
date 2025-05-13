One of the [[Coroutine]] constuctors that allow to catch the exception: 

The same as the `SuperviserJob()

```kotlin
superviserScope {
	launch {
		delay(100)
		throw Exception()
	}
	launch {
		delay(200)
		print('that code will execute despite of the exception')
	}
}
```
