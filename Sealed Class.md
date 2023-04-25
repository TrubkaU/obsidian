A part of the [[00 Kotlin]] language

The sealed class looks pretty much the same as the enum class but there are differences.
1. All Enum class members is singletons, sealed class members can be singletons, but it is possible to make a regular class as the sealed class member. That means a such class in the sealed can have a lot of exemplars
2. Since the sealed class members can have a lot of exemplars, it is possible to set different values for the class fields, and it means it allows to work with regular classes as the enum members.
3. The sealed classes are super useful together with `when` construction.
4. Also, there are sealed interfaces.