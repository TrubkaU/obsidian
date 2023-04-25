How to optimize the [[00 Android]] resources?

Great article https://google-developer-training.github.io/android-developer-advanced-course-concepts/unit-2-make-your-apps-fast-and-small/lesson-4-performance/4-3-c-best-practices-network-battery-compression/4-3-c-best-practices-network-battery-compression.html#network

1. Network calls should be optimized
	1. Send data in a bundle, collect and then send it together, for analytic purposes
	2. No double calls
	3. Use caching data instead of calling constantly
	4. Don't download large files trow the mobile provider, download large data from the WiFI.
	5. Optimize the image size for download
2. Use the WebP images instead of JPG
3. Optimize the PNG image quality.
4. Don't use vector graphics more than 200x200
5. Avoid nested views, use the RelativeLayout instead of nested several LinearLayouts.
6. Use the <merge> tag for the custom view or for a complicated view to avoid additional nested constructions
7. Be sure that the all dependencies in your project really need. If you are faced with a 64k issue, it's a point to analyze the dependencies.
8. Use the AAR instead of APK for Stores. It will prepare a specific app for the device directly