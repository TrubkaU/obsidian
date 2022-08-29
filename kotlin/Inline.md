Inline modifier uses in [[00 Kotlin]] to place method directly to the place, where it was called
- the function, that use the inline will enter directly to the code
- its possible to call return from the extention, calls  `Non-local returns`

How it looks like:
```(kotlin)

inline fun String.getSomething(block: () -> Unit) {
	// do something
}

```

Profs: 
- no need to create anonimous classes for lambda, which can be provided to the constuctor
- support [[Refied]] means it possible to know the type of generic, and use operator is, instead of using the reflextion. 

Cons:
- the size of code will grow since all inline function will enter directly to the code
- no need to use inline for the methods, where no input lambdas as the parameter since no profits cause no anonimous classes
- also, if the inline function placed into the different module, and you use those, it possible that current module 