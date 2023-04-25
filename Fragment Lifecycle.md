[[Fragment]] have two lifecycles FragmentLifecycle and FragmentViewLifecycle:

![[Pasted image 20230328133745.png]]

The idea to use `onViewCreated()` is here the view is already created and ready to use.

How to place fragments:
1. Use the FragmentContainerView in XML layout
2. Use the FragmentManager for adding the fragment
3. Or you can use the Jetpack Navigation

FragmentManager add, replace 


What's going on with Fragment View if the fragment will go to the stack?