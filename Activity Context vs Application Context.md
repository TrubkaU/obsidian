[[00 Android]] provides two types of context: [[Activity]] Context and Application context.

Activity Context has the UI lifecycle, but the Application does not. 
**Activity Context: 
```
Load Resource Values,  
Layout Inflation,  
Start an Activity,  
Show a Dialog,  
Start a Service,  
Bind to a Service,  
Send a Broadcast,  
Register BroadcastReceiver.
```

Application Context:
```
Load Resource Values,  
Start a Service,  
Bind to a Service,  
Send a Broadcast,  
Register BroadcastReceiver.
```

Don't use Application Context in Singletons of course!
