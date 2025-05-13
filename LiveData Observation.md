
There is an issue with observing the [[LiveData]] in [[Fragment]].

Since the Fragment has its own [[Fragment Lifecycle]] and the viewLifeCycle, should be careful to subscribe:
```kotlin
class MyActivity : AppCompatActivity() {  
    
	override fun onCreate(savedInstanceState: Bundle?) {  
		  
		// Improper observation  
		viewModel.myLiveData.observe(this, Observer { data ->  
		// Update UI - This can cause a memory leak if not handled correctly 
		//  
		})  
	}  
}
```

So, use the `viewLifecycleOwner` instead.
```kotlin
class MyFragment : Fragment() {  
  
  
	override fun onViewCreated(view: View, savedInstanceState: Bundle?) {  
	  
		viewModel.myLiveData.observe(viewLifecycleOwner, Observer { data ->  
		// Update UI - Correctly observing with viewLifecycleOwner  
		})  
	}  
}
```
