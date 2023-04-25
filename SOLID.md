### S - Single Resposibility


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
```


### O - Open to Extention Close to Modification

Class should be open to Extention but closed to modification:
```kotlin
class enum MessageType {
	EMAIL, SMS
}
// Open-closed principle corrupted
class MessageSerivce {
	fun send(text: String, type: MessageType) {
		when(type) {
			EMAIL -> sendEmail(text)
			SMS -> sendSms(text)
		}
	}
}
// Better solution
interface MessageService {
	fun send(text: String)
}

class EmailMessageService: MessageService {
	@Override
	fun send(text: String)
}

class SmsMessageService: MessageService {
	@Override
	fun send(text: String)
}
```

### L - Liskov Substitution
If you have some kids from the object, those kids have to work correctly in the program, independent of what thing you use, parent or child.

```kotlin
class Account {
	fun getBalance(): BigDecimal
	
	fun add(amount: BigDecimal)
}

class FirstAccount : Account() {
	
	@Override fun getBalance(): BigDecimal
	
	@Override fun add(amount: BigDecimal)
}

class SecondAccount : Account() {
	@Override fun getBalance(): BigDecimal
	// corrupted Liskov principle	
	@Override fun add(amount: BigDecimal) {
		throw IllegalStateException() // not supported by some reasons
	}
}
```



### I - Interface Segregation
```kotlin
interface Payments {
	fun payPal()
	fun cash()
}

interface InternetPayment {
	fun payPal()
}
interface OtherPayment {
	fun cash()
}
```

### D - Dependency Inversion
Use the interfaces instead of the real class:
```kotlin
interface Keyboard { }

class EngKeyboard : Keyboard

class Windows98Machine (val keyboard: Keyboard) 

fun main() {
	Windows98Machine(EngKeyboard())
}
```

#### Controversial points

As the result, the code will be complicated and extra complicated. 
No reasons to create extra levels