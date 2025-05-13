See also [[Reference types]]

`WeakHashMap` is based on `WeakReference` from the `java.lang.ref` package.

In a `WeakHashMap`, map keys are [[WeakReference]] objects. If there are no strong references to a key, then all values associated with that key will be automatically removed from the `WeakHashMap`.

This makes `WeakHashMap` a convenient choice for caching data, allowing unused data to be garbage collected automatically.


