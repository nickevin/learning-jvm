
##### JVM Options
* -Xms256m
* -Xmx512m
* -Xss256k
* -XX:PermSize=128m
* -XX:MaxPermSize=128M
* -XX:SurvivorRatio=7
* -XX:NewRatio=2
* -XX:MaxTenuringThreshold=8

![heap_dump](http://7d9k2r.com1.z0.glb.clouddn.com/jvm_heap_dump.png)

##### Explain
* Young Gen: 170.626, 85.356
	- Eden Space: 132.750, 66.438
	- Survivor: 37.876, 18.876
		- Survivor 0: 18.938, 9.438
		- Survivor 1: 18.938, 9.438
* Old Gen: 341.375, 170.688
* Perm Gen: 128, 128
* -Xms: 85.356 + 170.688 = 256.044
* -Xmx: 170.626 + 341.375 = 512.001
* -XX:SurvivorRatio=7
	- Eden: Survivor = 7: 2
	- Eden: 170.626 * 7/9 = 132.22, 85.356 * 7/9 = 66.388
	- Survivor: 170.626 * 2/9 = 37.917, 85.356 * 2/9 = 18.968
* -XX:NewRatio=2
	- Young Gen: Old Gen= 1: 2
	- 170.626: 341.375= 1:2
	- 85.356: 170.688= 1:2

##### Reference
* [JVM Settings](http://jvmmemory.com/)
* [Java Options](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/java.html)
* [JDK Tools and Utilities ](https://docs.oracle.com/javase/8/docs/technotes/tools/#basic)
* [Java HotSpot VM Options](http://www.oracle.com/technetwork/java/javase/tech/vmoptions-jsp-140102.html)
* [JVM调优总结](http://unixboy.iteye.com/blog/174173/)
* [GC大揭秘](http://longdick.iteye.com/blog/474764)
