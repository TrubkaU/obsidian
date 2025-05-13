One of the  [[Android Components]] that allow getting events from the Android Operation System, like enabling WiFi, getting the call, etc. 

Broadcast Receiver gets the Intent and usually has the same priority, as the [[Activity]]


How to work with:

1. register in Manifest with Intentfilter
2. Inherited own class from  BroarcastReceiver 
3. register it in the [[Activity]] with IntentFilter
4. don't forget to unregister it in the onDestroy()
5. send the intent with the same action as in the IntentFilter to catch the Intent into your BroadcastReceiver

***Memory Leaks

Don't forget to unregister Receiver, otherwise it would lead to [[Memory Leaks]]
```kotlin
class MyActivity : AppCompatActivity() {  
  
	private val myReceiver = object : BroadcastReceiver() {  
		override fun onReceive(context: Context?, intent: Intent?) {  
		// Handle the broadcast  
		// Here is the Implicit Reference to the Activity!!! Potential Bug!!!
		}  
	}  
	  
	override fun onCreate(savedInstanceState: Bundle?) {    
		IntentFilter(Intent.ACTION_AIRPLANE_MODE_CHANGED).also { filter ->  
			registerReceiver(myReceiver, filter)  
		}  
	}  
	  
	override fun onDestroy() {  
		super.onDestroy()  
		unregisterReceiver(myReceiver) // Unregister the receiver  
	}  
}
```
