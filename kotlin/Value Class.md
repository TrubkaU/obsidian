[[00 Kotlin]]
Problem:
		you can call:
```kotlin
fun callMethod(val name: String)
```
		But potentially, instead of String, you can use:
		* data class
		* value class
		* typealias
		
		
```kotlin
data class Name(val name: String)
fun callMethod(val name: Name)
```
But it's a bit slowly

```kotlin
typealias Name = String
fun callMethod(val name: Name)
```
It's work fast, but it possible to set String

```kotlin
@JvmInline
value class Name(val name: String)
fun callMethod(val name: Name)
```
It works fast, and impossible to set String

Here a good article:
https://quickbirdstudios.com/blog/kotlin-value-classes/