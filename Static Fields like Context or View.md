The static fields: View or Context

```kotlin
class MyActivity : AppCompatActivity() {  
  
	companion object {  
		// Static reference to a View  
		var staticView: View? = null  
	}  
	  
	override fun onCreate(savedInstanceState: Bundle?) {  
		super.onCreate(savedInstanceState)  
		setContentView(R.layout.activity_my)  
		  
		staticView = findViewById(R.id.myView) // Assigning a view to the static field  
	}  
}
``
