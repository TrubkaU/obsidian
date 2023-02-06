[[00 Android]] provides two types of bindings:
1. Data Binding
2. View Binding

### Data Binding
Is a part of #Jetpack
The Data Binding is based on an Observable pattern.

Data binding connects data and UI in two ways, or possibly connecting in one way, from data to UI.
The `LiveData` provides the interface to bind data to the UI.
The LiveData should subscribe to the View Lifecycle 

The syntaxis allows using the data directly in the layout files.

#### Binding Adapters:
Needs to adapt data between View and LiveData.

### ViewBinding
Is a way to call the UI directly from the code.
example: 
```kotlin
viewBinding.recycler
```

Looks pretty similar to the deprecated [[Kotlin Synthetic]]

Don't forget to unbind the Views in `onDestroyView()` method. And then mark it as null.

Cons:
1. Will generate extra classes for all UI elements. That will affect the 64k issue and 

Profs:
1. Easy way to get access to the UI component

