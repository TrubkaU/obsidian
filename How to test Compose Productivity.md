Write benchmarks for [[Compose]] screens, it allows you to measure at least critical screen speed.

The main idea of that [[Benchmark]] pretty same as the UI tests on [[Espresso]]:

``` kotlin
benchmarkRule.measureRepeated(packageName = PACKAGE_NAME,  
metrics = list0f(FrameTimingMetric()),  
compilationMode = compilationMode,  
iterations = ITERATIONS,  
setupBlock = {...}  
) {  
val lazyColumn = device.findObject(By.res("list"))  
repeat(3) {  
lazyColumn.drag(  
Point(0, lazyColumn.visibleCenter.y / 3)  
)  
}  
}
```