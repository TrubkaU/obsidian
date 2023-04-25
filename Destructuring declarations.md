The way to decomposite objects to readable view. [[00 Kotlin]] using it
A simple example is:
```
val (one, two) = Pair<Int, Int>
```

Also, it works for the [[Data class]]:
```
data class SomeData(val one: Int, val two: Int)

val (one, two) = SomeData("one", "two")
```