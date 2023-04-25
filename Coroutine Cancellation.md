Also, the [[Throwable]] can be useful for that task

1. You can run [[Coroutine]] in two ways:
```kotlin
coroutineScope.launch {

}
val deffered = coroutineScop.async {

}
defffered.await()
```
2. There are two ways how to catch the Exception in coroutine
	1. try/catch 
	2. [[CoroutineExceptionHandler]]
3. Since [[Coroutine Continuation]]  will cancel all parent jobs, those jobs will be canceled too:
```kotlin
val errorHandler = CoroutineExceptionHandler { _, throwable ->_ }
CoroutineScope(Dispatchers.Main + errorHandler).launch {
	launch {
		throw Exception("Some Error")
	}
	launch {
		callSomething() // never called
	}
}
```
4. If you try to catch the exception by try/catch it will never work since [[Coroutine Continuation]]:
```kotlin
viewModelScope.launch {
	try {
		launch {
			throw Exception("Some Error")
		}
	} catch (e) {
		// doesn't catch here
	}
	callMethod()// that code will never called
}
// the exception will go to the parent coroutine
```
5. You are able to catch the exception in the coroutine block:
```kotlin
viewModelScope.launch {
	launch {
		try {
			throw Exception("Some Error")
		} catch (e) {
			// doesn't catch here
		}
	}
}
```
6. There are ways to escape canceling next coroutines:
```kotlin
CoroutineScope(Dispatchers.Main + errorHandler).launch {
	launch(SuperviserJob()) {
		throw Exception("Some Error")
	}
	launch {
		// code will run since superviserJob will break the coroutine continuation 
	}
}

CoroutineScope(Dispatchers.Main + errorHandler).launch {
	superviserScope { // that scope will break the chain jobs
		launch() {
			throw Exception("Some Error")
		}
		launch {
		// code will run since superviserJob will break the coroutine continuation 
		}
	}
}
```
7. Cacell job under the hood is a typical exception.

