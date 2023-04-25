
[[Process Interaction]]


Process lifecycle:

![[Pasted image 20230217160528.png]]

Process Priority [[Android Proces and Priority]]

![[Pasted image 20230217161018.png]]

1. It is possible to run two apps from one process, but it #deprecated from the [[API29]] 
2. It is possible to run  [[Android Components]] for one App with different processes. Need to set tag `android:process=child1` in AndroidManifest.xml 
3. But for that case the resources will be not the same, which 
4. means the DI tree will be duplicated since each process has own resources
