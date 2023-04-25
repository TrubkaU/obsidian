



## ConcatAdapter
https://developer.android.com/reference/androidx/recyclerview/widget/ConcatAdapter

You can merge several adapters in one and it's possible to create a Header and a Footer for the List.





## Blinking 
Is an [[Errors]] that appears in RecylcerView
Sometimes an item can start blicking when updated one element on the item is.
It appears that the Recycler tried to animate changing content on the item despite that the content on the item is still the same and has been changing only a small element on the view.

One of the fixes is to control the payload in the RecylcerView:

https://www.valueof.io/blog/recyclerview-diffutil-change-payloads




