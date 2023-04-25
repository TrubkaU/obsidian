[[00 Android]] declares how to create a [[Fragment]]s:

Classic way: 
` class SomeFragment: BaseFragment()`
The constructor must be empty since Android can create the Fragments after rotating the device.

But how to provide some dependencies to the Fragment?
I know at least 3 ways:
1. Use the Dependency Injection framework, like [[Hilt vs Dagger]], or [[Koin]]
``` Kotlin
class SomeFragment: BaseFragment() {

	@Inject lateinit var someRepo: SomeRepo
}
```
2. Use the FragmentFactory:
``` Kotlin

class SomeFragment(var someRepo: SomeRepo): BaseFragment()

class CustomFragmentFactory(val someRepo: SomeRepo) : FragmentFactory() {

	override fun instantiate(
		clsLoader: ClassLoader, 
		className: String
		): Fragment 
	{
		if (className == SomeFragment::class.java.name) {
			return SomeFragment(dependency)
		}
	
		return super.instantiate(classLoader, className)

	}
}
```
And use the CustomFragmentFactory in the Activity:
``` Kotlin
class MyActivity : AppCompatActivity() {
	override fun onCreate(savedInstanceState: Bundle?) {
		supportFragmentManager.fragmentFactory = customFragmentFactory
		super.onCreate(savedInstanceState)
	}
}
```

Great article I found here: https://proandroiddev.com/android-fragments-fragmentfactory-ceec3cf7c959
