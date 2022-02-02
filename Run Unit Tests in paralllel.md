Run [[00 Android]]Unit Tests in parallel is not trivial task since tests runs by [[00 Gradle]].
But Gradle can't run it in parallel easy.
Instead of that the Gradle can run tests by package, some prefix or something else, but no way to run scope of tests from different packages.
But there is a way to use the Junit Categories, that help to separate tests.
Also, a good article describes how it possible: https://prandroid.dev/Parallel-unit-tests-in-android/