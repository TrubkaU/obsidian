Framework from [[00 Kotlin]] that allows the [[00 Android]] to work with asynchronous code more effectively.

##### What is suspend under the hood?
```kotlin
suspend fun myFun() { }
```
In fact in Java is:
```java
   public void simple(Continuation completion) { }  
```
So, it means any suspend in real life provides Continuation interface: [[Coroutine Continuation]]

##### There are several ways to execute suspend functions in code:
1. run suspend function into another suspend function
2. run suspend into runBlocking {}
3. run suspend into the CoroutineScope
4. for the ViewModel  it's a viewModleScope

Coroutine Builders:
```kotlin
withContexnt(Dispatchers.IO) {

}
```

```kotlin
coroutineScope {

}

supervisorScope {

}
```

```kotlin
val job = SupervisorJob()
val scope = CoroutineScope(Dispatchers.IO + job)  
scope.launch {  
  
}
val deferred: Deferred<T> = scope.async {

}
deferred.await()
```

```kotlin
runBlocking {
 //don't use it in production code. only for tests
}
```


Also, there is a [[Coroutine Dispatchers]]
Several words about [[Coroutine Jobs]]
Handle Coroutine Exception:

use try/catch




