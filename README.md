# [Spark - Scala -Gradle](https://medium.com/@yanggao1119/using-gradle-to-create-a-simple-scala-spark-application-d5f1740e741b)


1. Created new gradle project (groovy) , set gradle jdk to JAVA_HOME .
2. Configured version controlling in intelliJ using ssh token to github .
3. Created local branch and working on locally in project .
4. Committing changes and pushing new branch to GitHub
5. Merging changes to main via PR from feature branch (dev) .

Anyone can fork this feature branch and suggest changes to it by a pull request  .

### Issues faced :
1. brew installed java path is not showing for Gradle sdk path in intelliJ (opt folder is not showing)-> /opt/homebrew/opt/openjdk@11/bin/java
   https://intellij-support.jetbrains.com/hc/en-us/community/posts/360007751379/comments/360001527259 . 
Created a symlink to brew path and set it as JAVA_HOME and GRADLE jdk . IntelliJ points to /opt/homebrew path .
We need to have standard layout structure in it , which will be find under `libexec`,brew usually installs the standard layout copy there. 
```
<user>@Neethu-machine ~ % ls -ltr /Library/Java/JavaVirtualMachines/openjdk-11.jdk
total 0
lrwxr-xr-x  1 root  wheel  48 Dec 23 22:21 openjdk.jdk -> /opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk
```
2. "Module spark-scala-gradle is imported from Gradle. Any changes made to its configuration may be lost after reimporting." -- (https://intellij-support.jetbrains.com/hc/en-us/community/posts/360000526410-Adding-dependancies-in-Project-Structure-does-not-update-build-gradle)


```
Check Gradle JVM and language level
Gradle JVM: when IntelliJ IDEA opens the Gradle project, it checks the gradle.properties file for the appropriate JVM version specified in org.gradle.java.home and uses it for the project. If it is not specified, then the project SDK is used. Alternatively, you can use the Gradle settings to configure the Gradle JVM.
Language level: the language level settings are applied for a source root or for a module. If a Gradle project has a single linked project then the project default language level is set to the minimum language level among the module language levels. The module language level is set to sourceCompatibility in the build.gradle file.
The preview part is set to the conjunction of preview flags of the module source sets. The source set module language level is set to the corresponding combination of sourceCompatibility property and --enable-preview flag.
```
3. Caused by: java.lang.reflect.InaccessibleObjectException: Unable to make private java.nio.DirectByteBuffer(long,int) accessible: module java.base does not "opens java.nio" to unnamed module @28c71909

   Resolved by step 1. 
