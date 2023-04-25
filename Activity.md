Is one of the App components for [[00 Android]] platform.

Also, AppCompatActivity, FragmentActivity, ComponentActivity

ComponentActivity: work with [[Compose]] without XML layouts. 


`AppCompatActivity() : FragmentActivity() : ComponentActivity() : Activity()`

ActionBarActivity

During rotation, the ViewModel will be saved into the static holder, calls #screen_rotation 
```java
static final class NonConfigurationInstances {  
    Object custom;  
    ViewModelStore viewModelStore;  
}
```
That is stored in the `ComponentActivity`