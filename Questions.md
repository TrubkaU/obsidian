Where are the [[ViewModel]] stores?

the classic way to get the ViewModel is by using the ViewModelProvider
```kotlin
ViewModelProvider(aViewModelStoreOwner).get(MyViewModel::class.java)
```

But [[Activity]], `Fragment`, and `NavBackStackEntity` provide the `ViewModelStore`, which retains the VM in hashMap.

What happens with Activity and the Fragment when the device is rotated? #screen_rotation


How to work in Android with different screen sizes?

Say about your success and failure story.


