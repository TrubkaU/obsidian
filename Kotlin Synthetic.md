Feature, that provides by [[00 Kotlin]] as the plugin. 
#deprecated till the end of 2022.

Generate the static classes for UI components.

Main problem:
1. Basically it generates static classes that keep the link to the UI elements, and it initializes once but in the real world, View may be nullable in some cases.
2. Since it is based on the View names it is possible that the different layouts have the same names, and it is possible to use the view from another layout and it will lead to a null pointer exception.

In general, instead of Kotlin Synthetic should use the View Binding


Here is the article that describes the reasons why one should migrate from Kotlin synthetics: https://developer.android.com/topic/libraries/view-binding/migration
