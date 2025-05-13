An Abstraction for Interacting with Data in [[00 Android]] OS
This appears since the app interacts with another process by [[IPC]] 

To collect the current number of FileDescriptors for the app, execute the following:

```bash
adb shell su 
ls -l /proc/${APP_PID}/fd | wc -l`
```

Where `APP_PID` is the application’s process identifier.

If an app has 300 or more open FileDescriptors, it may indicate a [[Memory Leaks]] issue.

<span style="color:red">There are restrictions for the app: No more than 1024 FileDescriptors, and in some cases, no more than 500.</span>

An overflow in the count leads to the following exception:

`java.lang.RuntimeException: Too many open files`

To keep the number of open FileDescriptors at a reasonable level, follow these guidelines:

- Use the Kotlin `use` function to work with resources.
- In Java, use the "try-with-resources" statement.
- Disconnect the `HttpUrlConnection` after completing the call.
- Use a limited number of [[Threads]] with a Handler/Looper. Each `Looper.prepare()` opens a FileDescriptor.
- Control the number of threads via ExecutorServices, as each thread opens a FileDescriptor.
- Close the WebSocket after use.
- Ensure the `SqliteDatabaseConnection` is a singleton.
- Prevent [[Memory Leaks]].

Source: [Habr Article](https://habr.com/ru/articles/749568/)