#### How to return to the Main Thread:
1. Use the Activity:
```kotlin
activity.runOnUiThread(Runnable)
```
2. By the Handler Looper
```kotlin
val handler = object : Handler(Looper.getMainLooper()) {

	override fun handleMessage(msg: Message) {
			// handle the msg 
	}
}

Thread {
	handler.postMessage(SomeMessage())
}.start()

handler.post(Runnable)

```
3. Use the LiveData:
```kotlin
val liveData = MutableLiveData<Boolean>()
liveData.post(true)

liveData.observe(view.lifecycleOwner) { it ->
	it is Boolean
}

```
4. Use [[Coroutine]]:
```kotlin
val scope = CoroutineScope(Dispatchers.IO)
scope.launch {
	// do something
	withContext(Dispather.Main) {
		// here you are in Main Thread
	}
}
```
5. Use [[Flow]]:
```kotlin
val flow = flow {  
    // IO Thread  
    emit(1)  
}.flowOn(Dispatchers.IO)  
  
CoroutineScope(Dispatchers.Main).launch {  
    flow.collect {   
		// Main Thread  
    }  
}
```
6. Use the [[RxJava]]
```kotlin
val single = Single.just(true)

single
	.map {
		// IO Thread
	}
	.subscribeOn(Schedulers.io())
	.observeOn(AndroidSchedulers.mainThread())
	.subscribe {
		// Main Thread
	}
```
7. Use the [[Broadcast Receiver]]
```kotlin
class MyReceiver : BroadcastReceiver() {  
  
    override fun onReceive(p0: Context?, p1: Intent?) {  
        // here UI Thread
    }  
}

val receiver = MyReceiver()  
  
registerReceiver(receiver, IntentFilter("my.custom"))  
  
Thread {  
    sendBroadcast(Intent("my.custom"))  
}.start()
```

#### How Thread work

