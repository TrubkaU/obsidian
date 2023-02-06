Run [[00 Android]]Unit Tests in parallel is not a trivial task since tests run by [[00 Gradle]].
But Gradle can't run it in parallel easily.
Instead, the Gradle can run tests by package, some prefix or something else, but no way to run the scope of tests from different packages.
But there is a way to use the Junit Categories, that help to separate tests.
Also, a good article describes how it is possible: https://prandroid.dev/Parallel-unit-tests-in-android/ but it works only for Junit4

For Junit5 should use the @Tag mechanism


Here a good article https://www.softwaretestinghelp.com/junit-test-suite/