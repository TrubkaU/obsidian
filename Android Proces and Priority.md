The source: https://medium.com/androiddevelopers/who-lives-and-who-dies-process-priorities-on-android-cb151f39044f

[[00 Android]] has a priorityes pyramid for the processes that run on the device:

![[Pasted image 20230206124934.png]]

1. Foreground means Activity between onResume and onPause. Or if [[Service]] was bonded from such [[Activity]] means the Service will get the same Foreground priority. Briefly, all components which will run from that Activity will have the same priority.
2. Visible Process means Activity between onStart and onStop. Typical example, after display popup the Activity will be moved from Foreground to Visible
3. Typically it's a [[Service]] that runs as the Background. 
4. Background Process is an Activity after onStop. 
5. Empty Process is a process without any Activity or [[Broadcast Receiver]] or other components

Several good tricks:
Display all processes and filter by package:

`adb shell ps | grep com.example.packagename` 