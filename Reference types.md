Java provides 4 types of references:
1. Strong Reference
2. WeakReference
3. SoftReference
4. PhantomReference

Each of these references is collected in a different way by the garbage collector.


WeakReference used for WeakHashMap, details in [[HashMap]]
For Android, it is possible to set Activity as the WeakReference for example to the ViewModel or AsyncTask despite that it's an anti-pattern, but it will allow avoiding memory leaks.

```java
private class MyAsyncTask extends AsyncTask<String, Void, Void> {

    private WeakReference<Activity> mActivity;

    public MyAsyncTask(Activity activity) {
        mActivity = new WeakReference<Activity>(activity);
    }

    @Override
    protected void onPreExecute() {
        final Activity activity = mActivity.get();
        if (activity != null) {
            ....
        }
    }
```


SoftReference can help to organize caching of the data. Despite that, the object will no longer have Strong References, but the Garbage Collector will collect the object only if the memory will ended. 

**Important**: But for [[00 Android]] Google recommends avoiding using the SoftReferences as the cache instrument. Use the [[LruCache]] instead. : https://developer.android.com/reference/java/lang/ref/SoftReference.html
