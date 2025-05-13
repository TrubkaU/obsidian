### S - Single Responsibility
[[Single Responsibility]]

### O - Open to Extention Close to Modification

The class should be open to Extention but closed to modification:
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
[[Dependency Inversion]]
### Controversial points

As the result, the code will be complicated and extra complicated. 
No reasons to create extra levels