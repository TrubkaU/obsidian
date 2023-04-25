Interaction between [[Process]] by the IPC 
1. Send Intent by Extra. It is possible to send [[Serializable vs Parcelable]] data only not more than 500 kb. It's an Asynchronous solution. Work with Bundle
2. [[Content Provides]] . SMS, Phone Book. Content Provider return Cursor
3. Messanger: ![[Pasted image 20230217163723.png]]
The Service should work in Process B. You should bind from process A to process B and get the Messanger instance that will allow sending the messages from process A to process B. Working with Bundler, Int, means only Parcellable. Possible to send data in two ways. 

### BINDER
![[Pasted image 20230217171822.png]]


![[Pasted image 20230217173155.png]]