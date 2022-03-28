# CCTrackingLibrary

Automatically analyze the third-party application libraries involved in iOS/macOS executable binary files,
and support multi file parsing. Support MacOS / x86-64 and detect x86-64 / arm64 files.
Binary is written in Objective-C/Swift language. It can be used as a normal binary file or after iOS jailbreak (...) binary file. 
It can involve app competitive product analysis, reverse learning tracking, etc.

自动分析iOS/macOS可执行二进制文件所涉及的第三方应用库，支持多文件解析。支持macOS/x86-64,可探测x86-64/arm64文件。
二进制使用Objective-C/Swift语言编写的，可以正常二进制文件或iOS越狱后(...)的二进制文件。可涉及app竞品分析，逆向学习追踪等。

```shell
CC # ls
CCTestBin1		CCTestBin2		CCTrackingLibrary
CC # ls -l
total 167752
-rw-r--r--@ 1 cc  staff  38273984 Mar 28 18:07 CCTestBin1
-rw-r--r--  1 cc  staff  37665360 Mar 28 18:07 CCTestBin2
-rwxr-xr-x  1 cc  staff   9944608 Mar 28 18:04 CCTrackingLibrary
CC # file *
CCTestBin1:        Mach-O 64-bit executable arm64
CCTestBin2:        Mach-O 64-bit executable arm64
CCTrackingLibrary: Mach-O 64-bit executable x86_64
CC # CCTrackingLibrary CCTestBin1 | head  -3
001: AFNetworking
002: CocoaAsyncSocket
003: DACircularProgress
CC # CCTrackingLibrary CCTestBin2 | tail  -3
44: YYWebImage
45: ZipKit
46: nanopb
CC #  (CCTrackingLibrary CCTestBin1 | head -3) &&  (CCTrackingLibrary CCTestBin2 | tail -3)
001: AFNetworking
002: CocoaAsyncSocket
003: DACircularProgress
44: YYWebImage
45: ZipKit
46: nanopb
CC #
```

