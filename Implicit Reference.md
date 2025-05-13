Be careful with anonymous classes, anonymous listeners,  [[Handlers]], Runnable, all of they contain the implicit reference to the [[Activity]] or Fragment.

``` kotlin
class MyActivity : AppCompatActivity() {  
  
	override fun onCreate(savedInstanceState: Bundle?) {  
		super.onCreate(savedInstanceState)  
		setContentView(R.layout.activity_my)  
		  
		val button = findViewById<Button>(R.id.myButton)  
		button.setOnClickListener {  
		// This is an anonymous inner class  
		// It holds an implicit reference to MyActivity  
		// Long-running operations or delayed execution here can cause leaks  
			someDelayWork() // will lead to potential problem if activity should be destroyed
		}  
	}  
}
```

So, the fix is to use the [[WeakReference]]
```kotlin
class MyActivity : AppCompatActivity() {  
  
	override fun onCreate(savedInstanceState: Bundle?) {  
		super.onCreate(savedInstanceState)  
		setContentView(R.layout.activity_my)  
		  
		val button = findViewById<Button>(R.id.myButton)  
		button.setOnClickListener(ButtonListener(this)) 
	}  
	  
	private class ButtonListener(activity: MyActivity) {  
		private val activityReference = WeakReference(activity)  
	
	override onClick(view: View) {
		activityReference.get()?.let {
			// do work here
		}
	}  
}
```
