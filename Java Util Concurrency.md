1. RentalLock: pretty similar as the syncronized
```kotlin
val mutex = RentalLock()

mutex.lock()
// start syncro code
mutex.unlock()
// here code is async
```
 
2. Semaphore: similar as the RentalLock, but allows to set number of threads to use the synch code.
```kotlin
val mutex = Semaphore(2)

mutex.acquire()

mutex.release()
```

## Concurrent Collections
