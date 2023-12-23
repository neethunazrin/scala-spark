# [Spark - Scala -Gradle](https://medium.com/@yanggao1119/using-gradle-to-create-a-simple-scala-spark-application-d5f1740e741b)


1. Created new gradle project (groovy) , set gradle jdk to JAVA_HOME .
2. Configured ssh token with GitHub .
3. Created local branch and working on locally in project .
4. Committing changes and pushing new branch to GitHub
5. Giving PR for review to collaborators of same project .



```
Issues faced :
1. brew installed java path is not showing for Gradle sdk path in intelliJ (opt folder is not showing)-> /opt/homebrew/opt/openjdk@11/bin/java 
https://intellij-support.jetbrains.com/hc/en-us/community/posts/360007751379/comments/5199670293522 . 
So, downloaded new jdk path under user library and set as JAVA_HOME .
2. "Module spark-scala-gradle is imported from Gradle. Any changes made to its configuration may be lost after reimporting." -- https://intellij-support.jetbrains.com/hc/en-us/community/posts/360000526410-Adding-dependancies-in-Project-Structure-does-not-update-build-gradle

```