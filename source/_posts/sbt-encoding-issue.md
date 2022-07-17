---
title: sbt encoding issue - Chinese words are not printed as expected
date: 2022-05-02 21:33:26
updated: 2022-07-17 14:17:47
categories:
  - [Scala]
  - [Chisel]
  - [sbt]
tags:
  - sbt
  - encoding
mathjax: false
---
# Issue details.
Date in Chinese is not printed as expected. Log for sbt command running in powershell is  given below.
```bash
PS E:\Workspaces\scala\chisel_helloworld> sbt 'testOnly gcd.GcdDecoupledTester'
[info] welcome to sbt 1.4.9 (Oracle Corporation Java 16.0.2)
[info] loading settings for project global-plugins from idea.sbt ...
[info] loading global plugins from C:\Users\zhangyb\.sbt\1.0\plugins
[info] loading settings for project chisel_helloworld-build from plugins.sbt ...
[info] loading project definition from E:\Workspaces\scala\chisel_helloworld\project
[info] loading settings for project root from build.sbt ...
[info] set current project to chisel_helloworld (in build file:/E:/Workspaces/scala/chisel_helloworld/)
[info] compiling 2 Scala sources to E:\Workspaces\scala\chisel_helloworld\target\scala-2.13\classes ...
[info] Non-compiled module 'compiler-bridge_2.13' for Scala 2.13.8. Compiling...
[info]   Compilation completed in 8.11s.
[info] compiling 1 Scala source to E:\Workspaces\scala\chisel_helloworld\target\scala-2.13\test-classes ...
[info] Run completed in 42 milliseconds.
[info] Total number of tests run: 0
[info] Suites: completed 0, aborted 0
[info] Tests: succeeded 0, failed 0, canceled 0, ignored 0, pending 0
[info] No tests were executed.
[info] No tests to run for Test / testOnly
[success] Total time: 15 s, completed 2022骞?鏈?鏃ヤ笅鍗?:56:52
```

# Ephemeral Solution
Run the following commands.
```bash
PS E:\Workspaces\scala\chisel_helloworld> set JAVA_TOOL_OPTIONS=-Dfile.encoding=UTF-8
PS E:\Workspaces\scala\chisel_helloworld> chcp 65001
Active code page: 65001
```

# Permanent Solution
Change System Locale to Use UTF-8 Encoding in Windows PowerShell.
- Go to Region Settings from the Control Panel.
- Open the Administrative tab and click Change system locale.
- Then check the Beta option as shown in the image below.![](/images/region.jpg)


For more details please refer to [UTF-8 Encoding (CHCP 65001) in PowerShell](https://www.delftstack.com/howto/powershell/powershell-utf-8-encoding-chcp-65001/).


# Done
Everything works fine now.

## Documents
- [How to set utf8 on windows?](https://github.com/sbt/sbt/issues/4322)
