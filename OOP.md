
Each modern lang, like [[00 Java]] or [[00 Kotlin]] based on the 3 principles: 
1. Encapsulation 
2. Inheritance
3. Polymorphism

#### Inheritance

```kotlin
class Parent {
	fun method()
}

class Child: Parent
	override fun method()
```

#### Encapsulation
Hide the data into the class and control getting and setting data by a special mechanism.

```kotlin
class SomeClass
	private var someValue: Int
	
	fun getValue(): Int
	
	fun setValue(value: Int)
)
```

#### Polymorphism

Overriding methods, 

```kotlin
class Parent {
	fun method()
}
class Child : Parent() {
	override fun method()
}
```