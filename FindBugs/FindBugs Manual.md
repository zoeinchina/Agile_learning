[TOC]

#What is FindBugs
FindBugs™ is a program to find bugs in Java programs. It looks for instances of "bug patterns" --- code instances that are likely to be errors.

**Requirements:**
- a runtime environment compatible with Java 2 Standard Edition, version 1.5 or later
- at least 512 MB of memory to use FindBugs

**Download** [FindBugs](http://findbugs.sourceforge.net/downloads.html) (Extract the zip file to local)

# Running FindBugs
**Direct invocation of FindBugs**
Double click the file: C:\Program Files\IBM\findbugs-3.0.1\lib\findbugs.jar

**Invocation of FindBugs using a wrapper script**
> C:\Program Files\IBM\findbugs-3.0.1\lib>cd C:/Program Files/IBM/findbugs-3.0.1/bin
> C:\Program Files\IBM\findbugs-3.0.1\bin>findbugs.bat

![](http://ww2.sinaimg.cn/large/76ea2b87gw1f5554asjiwj20m80i2gmd.jpg)

# Using FindBugs GUI
Open FindBugs GUI, click *File* -> *New Project*

![](http://ww1.sinaimg.cn/large/76ea2b87gw1f555qsod8pj20mb0hj3zu.jpg)

Click *Add* to select a Java archive file (zip, jar, ear, or war file) or directory containing java classes. Here we are trying to analyze 3 projects.

![](http://ww1.sinaimg.cn/large/76ea2b87gw1f5565xz9bij20m704y3yw.jpg)

Then Click *Analysis* to start Analyzing the project. 

![](http://ww1.sinaimg.cn/large/76ea2b87gw1f556xuhdnuj208v03l0sn.jpg)

Now you can see that FindBugs is telling you that some classes needed for analysis were missing.
That's because you should add additional Jar files or directories as "Auxiliary classpath locations" entries if the archives and directories you are analyzing have references to other classes which are not included in the analyzed archives/directories and are not in the standard runtime classpath. 

![](http://ww1.sinaimg.cn/large/76ea2b87gw1f5573qgb63j20im0d9tbu.jpg)

So here we add all the references and dependencies in "Auxiliary classpath locations".

![](http://ww4.sinaimg.cn/large/76ea2b87gw1f55740kjb6j20oi0503zb.jpg)
![](http://ww2.sinaimg.cn/large/76ea2b87gw1f557bygqarj20ok05275e.jpg)
![](http://ww4.sinaimg.cn/large/76ea2b87gw1f557dop8qjj20oj01lwej.jpg)

And Hooray! it works.

![](http://ww4.sinaimg.cn/large/76ea2b87gw1f5580x09icj20wm0nudip.jpg)

The upper left-hand pane of the window shows the bug tree, can be modified by click *View* -> *Group bugs by...*.
When a particular bug instance is selected in the upper left pane, you will see the bug description in the bottom pane. The source code pane on the upper right will show the program source code where the potential bug occurs.(*Here in the sample is blank because we are using jar files instead of java directories, therefore source is not available.*)
Click *File* -> *Save as ...* to save the bug results.

# Using FindBugs Eclipse Plugin
