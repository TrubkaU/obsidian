Don't forget destoy the WebView before the [[Activity]] will be destroyed.

```kotlin
class MyActivity : AppCompatActivity() {  
  
	private lateinit var myWebView: WebView  
	  
	override fun onCreate(savedInstanceState: Bundle?) {  
		myWebView = findViewById(R.id.myWebView)  
		myWebView.loadUrl("https://example.com")  
	}  
	  
	override fun onDestroy() {  
		myWebView.destroy() // Properly destroy the WebView  
		super.onDestroy()  
	}  
}
```
