Each class should have a single responsibility. In different cases, it will lead to growing the classes into the big object 

Benefits:
1. Easy test
2. Smaller classes
3. Better understanding

```kotlin
class Car {
	fun getModel(): String
	fun maxSpeed(): Int
	fun order() // two resposibilities
}

/* Split double responsibility by different classes */
class Car {
	fun getModel(): Model
	fun getSpeed(): String
}

class OrdferService {
	fun order(car: Car)
}