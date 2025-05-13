Don't forget to recycle the bitmap after completing it.

```kotlin 
class MyActivity : AppCompatActivity() {  
  
	private var myBitmap: Bitmap? = null  
	  
	override fun onCreate(savedInstanceState: Bundle?) {  
		myBitmap = 
		BitmapFactory.decodeResource(resources, R.drawable.large_image)  
		// Resize bitmap as needed before setting it to ImageView  
		imageView.setImageBitmap(myBitmap)  
	}  
	  
	override fun onDestroy() {  
		super.onDestroy()  
		myBitmap?.recycle() // Recycle the bitmap  
		myBitmap = null  
	}  
}
```