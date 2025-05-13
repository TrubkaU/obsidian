The top-level modules shouldn't know anything about the details of how the low-level modules work,
```kotlin
module Domain {

	data class SomeData(val id: Int)
	interface SomeAction {
		fun action(sdata: SomeData): Int
	}

	inner class Controller(val action: SomeAction) {
		init {
			val result = action.action(SomeData(1))
		}
	}
}

module Data {
	implement module 'Domain'

	class SomeDataImpl: SomeData {
		fun action(sdata: SomeData): Int {
			return sdata.id
		}
	}
}
```

One of the principal approaches for [[Clean Architecture]] 