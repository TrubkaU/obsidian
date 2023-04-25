[[00 Kotlin]] provides such a framework that helps work with asynchronous code. 
So, Coroutine Dispatchers is a Scope of the threads that users be able to use in [[Coroutine]]

There are four dispatchers:
1. Dispatchers.Main - > one thread 
2. Dispatchers.Default -> by default, usually the number of threads equals the number of CPU kernel number. The threads for that dispatcher have the highest priority
3. Dispatchers.IO -> by default 64 Threads, but the limit can be adjected by the special set
4. Dispatchers.Unconfined ->


```kotlin
withContext(Dispatchers.Main) { 
	val singleValue = intFlow
	.map { ... } // Will be executed in IO 
	.flowOn(Dispatchers.IO) 
	.filter { ... } // Will be executed in Default 
	.flowOn(Dispatchers.Default) 
	.single() // Will be executed in the Main
}
```

Actually, any disaptchers has methods:
