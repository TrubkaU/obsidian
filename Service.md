There are two categories:
#### Started

Service will run and no way to interrupt between Service and other app components.

1. Foreground Services: provide more highest priority, which allows to keep the Service in memory since the user gets some content from the user, like listen to the music
2. Background Services: may be closed at any time and open later since it depends on the RAM memory.

The Service will have the same priority as the [[Activity]] that was started the Service

#### Bounded

Services that allow to bound by the IBind interface, probably interrupt between application components.

Service Lifecycle:
![[Pasted image 20230220170234.png]]


## Intent Service vs Service

IntentService will work on another Thread
Service will work on the Main Thread

BindService be able to return IBinder to return From Service the result of the work

Also, there is a Messanger, that provides to send 





Bind Service Lifecycle
![[Pasted image 20230221104849.png]]

