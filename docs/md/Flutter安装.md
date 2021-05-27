<!--
 * @Author: tangdaoyong
 * @Date: 2021-05-18 18:06:27
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-05-27 10:18:05
 * @Description: Flutter安装
-->
<!-- TOC -->

- [Flutter安装](#flutter安装)
    - [MacOS](#macos)
        - [1. 下载flutter](#1-下载flutter)
        - [2. 配置环境](#2-配置环境)
        - [3. 验证配置](#3-验证配置)
        - [4. 开发二进制文件预下载（可选操作，建议选择）](#4-开发二进制文件预下载可选操作建议选择)
            - [4.1 设置镜像地址](#41-设置镜像地址)
        - [5. 运行 flutter doctor 命令](#5-运行-flutter-doctor-命令)
            - [5.1 配置Android环境](#51-配置android环境)
            - [5.2 更新CocoaPods](#52-更新cocoapods)
    - [问题](#问题)
        - [使用过程中发现：flutter pub get时比较慢](#使用过程中发现flutter-pub-get时比较慢)

<!-- /TOC -->
# Flutter安装

## MacOS

[Flutter MacOS 安装](https://flutter.cn/docs/get-started/install/macos)

### 1. 下载flutter

找一个文件夹使用`git`命令下载 `flutter` 版本可以自己选择。
```
// 下最新版本
git clone https://github.com/flutter/flutter.git
// 下稳定版本
git clone https://github.com/flutter/flutter.git -b stable --depth 1
```

### 2. 配置环境

* 编辑(使用的是`zsh`) `.zshrc` ，添加 `PATH`。

```shell
# 查看 `.zshrc`
cat ~/.zshrc
# 内容
export PATH=$HOME/bin:/Users/matias/.matias_shell:$PATH
# 修改
vim ~/.zshrc
# 添加路径（i进入编辑模式，编辑之后esc退出，然后：进入命令模式，wq保存并退出）
export PATH=$HOME/bin:/Users/matias/.matias_shell:~/SDK/Git_Flutter_SDK/flutter/bin:$PATH
# 刷新
source ~/.zshrc
```
如上：

* 开始已经添加了一个自定义脚本路径（`/Users/matias/.matias_shell`）了。
* 后面又添加了一个`flutter`路径`~/SDK/Git_Flutter_SDK/flutter/bin`，即`git`下载`flutter`的路径。

### 3. 验证配置

```
which flutter
```
输入路径

### 4. 开发二进制文件预下载（可选操作，建议选择）

`flutter` 命令行工具会下载不同平台的开发二进制文件，如果需要一个封闭式的构建环境，或在网络可用性不稳定的情况下使用等情况，你可能需要通过下面这个命令预先下载 `iOS` 和 `Android` 的开发二进制文件：
```shell
flutter precache
Downloading Dart SDK from Flutter engine 323033b1459d637d36eadd0147170de5de672b3c...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  213M  100  213M    0     0   972k      0  0:03:44  0:03:44 --:--:-- 1184k
Building flutter tool...
Flutter assets will be downloaded from https://storage.flutter-io.cn. Make sure you trust this source!
Downloading Material fonts...                                    2,147ms
Downloading Gradle Wrapper...                                       77ms
Downloading android-arm-profile/darwin-x64 tools...              2,959ms
Downloading android-arm-release/darwin-x64 tools...              2,412ms
Downloading android-arm64-profile/darwin-x64 tools...            2,720ms
Downloading android-arm64-release/darwin-x64 tools...            2,376ms
Downloading android-x64-profile/darwin-x64 tools...              2,825ms
Downloading android-x64-release/darwin-x64 tools...              2,451ms
Downloading android-x86 tools...                                   19.5s
Downloading android-x64 tools...                                   19.1s
Downloading android-arm tools...                                    8.8s
Downloading android-arm-profile tools...                            4.9s
Downloading android-arm-release tools...                            3.4s
Downloading android-arm64 tools...                                 10.1s
Downloading android-arm64-profile tools...                          4.9s
Downloading android-arm64-release tools...                          4.0s
Downloading android-x64-profile tools...                            5.6s
Downloading android-x64-release tools...                            4.0s
Downloading android-x86-jit-release tools...                        6.4s
Downloading ios tools...                                           35.3s
Downloading ios-profile tools...                                   25.7s
Downloading ios-release tools...                                  178.8s
Downloading Web SDK...                                             29.9s
Downloading package sky_engine...                                1,085ms
Downloading flutter_patched_sdk tools...                            3.2s
Downloading flutter_patched_sdk_product tools...                    7.7s
Downloading darwin-x64 tools...                                    36.6s
Downloading libimobiledevice...                                    166ms
Downloading usbmuxd...                                              94ms
Downloading libplist...                                             88ms
Downloading openssl...                                           1,290ms
Downloading ios-deploy...                                          104ms
Downloading darwin-x64/font-subset tools...                      2,697ms
```
*注意*在国内需要使用到设置镜像如[中国使用Flutter](https://flutter.dev/community/china)所示。

#### 4.1 设置镜像地址
和`配置环境`步骤类似，添加两个环境变量
```shell
# 修改
vim ~/.zshrc
# 添加环境变量(镜像地址)
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
# 刷新
source ~/.zshrc
```

### 5. 运行 flutter doctor 命令

`flutter doctor` 命令用来查看当前环境是否需要安装其他的依赖（如果想查看更详细的输出，增加一个 -v 参数即可）：
```
flutter doctor
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 2.2.0, on macOS 11.1 20C69 darwin-x64, locale zh-Hans-CN)
[✗] Android toolchain - develop for Android devices
    ✗ Unable to locate Android SDK.
      Install Android Studio from: https://developer.android.com/studio/index.html
      On first launch it will assist you in installing the Android SDK components.
      (or visit https://flutter.dev/docs/get-started/install/macos#android-setup for detailed
      instructions).
      If the Android SDK has been installed to a custom location, please use
      `flutter config --android-sdk` to update to that location.

[!] Xcode - develop for iOS and macOS
    ! CocoaPods 1.9.3 out of date (1.10.0 is recommended).
        CocoaPods is used to retrieve the iOS and macOS platform side's plugin code that responds to your
        plugin usage on the Dart side.
        Without CocoaPods, plugins will not work on iOS or macOS.
        For more info, see https://flutter.dev/platform-plugins
      To upgrade see https://guides.cocoapods.org/using/getting-started.html#installation for
      instructions.
[✓] Chrome - develop for the web
[✓] Android Studio (version 4.0)
[✓] VS Code (version 1.55.0)
[✓] Connected device (1 available)

! Doctor found issues in 2 categories.
```
如上提示：
* 
* `iOS` 相关的 `CocoaPods` 版本过低了。 

#### 5.1 配置Android环境

1. 安装`Android Studio`

安装 `Android Studio` 默认配置如下。

```
Setup Type: Standard
SDK Folder: /Users/matias/Library/Android/sdk
JDK Location: /Applications/Android Studio.app/Contents/jre/jdk/Contents/Home
Total Download Size: 549 MB
SDK Components to Download: 

Android Emulator
  
295 MB

Android SDK Build-Tools 30.0.3
  
49.3 MB

Android SDK Platform 30
  
49.9 MB

Android SDK Platform-Tools
  
13.2 MB

Android SDK Tools
  
98.2 MB

Intel x86 Emulator Accelerator (HAXM installer)
  
603 KB

SDK Patch Applier v4
  
1.74 MB

Sources for Android 30

41.3 MB
```

2. 再次查看

```
flutter doctor
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 2.2.0, on macOS 11.1 20C69 darwin-x64, locale zh-Hans-CN)
[!] Android toolchain - develop for Android devices (Android SDK version 30.0.3)
    ✗ Android licenses not accepted.  To resolve this, run: flutter doctor --android-licenses
[✓] Xcode - develop for iOS and macOS
[✓] Chrome - develop for the web
[✓] Android Studio (version 4.0)
[✓] VS Code (version 1.55.0)
[✓] Connected device (1 available)

! Doctor found issues in 1 category.
```
3. 运行提示指令`flutter doctor --android-licenses`。

```
flutter doctor --android-licenses
Warning: File /Users/matias/.android/repositories.cfg could not be loaded.
7 of 7 SDK package licenses not accepted. 100% Computing updates...
Review licenses that have not been accepted (y/N)?
```
然后一路`y`到底，（回车不行，默认不是y）

4. 再次查看

```
flutter doctor -v
[✓] Flutter (Channel stable, 2.2.0, on macOS 11.1 20C69 darwin-x64, locale zh-Hans-CN)
    • Flutter version 2.2.0 at /Users/matias/SDK/Git_Flutter_SDK/flutter
    • Framework revision b22742018b (5 days ago), 2021-05-14 19:12:57 -0700
    • Engine revision a9d88a4d18
    • Dart version 2.13.0
    • Pub download mirror https://pub.flutter-io.cn
    • Flutter download mirror https://storage.flutter-io.cn

[✓] Android toolchain - develop for Android devices (Android SDK version 30.0.3)
    • Android SDK at /Users/matias/Library/Android/sdk
    • Platform android-30, build-tools 30.0.3
    • Java binary at: /Applications/Android Studio.app/Contents/jre/jdk/Contents/Home/bin/java
    • Java version OpenJDK Runtime Environment (build 1.8.0_242-release-1644-b3-6222593)
    • All Android licenses accepted.

[✓] Xcode - develop for iOS and macOS
    • Xcode at /Applications/Xcode.app/Contents/Developer
    • Xcode 12.4, Build version 12D4e
    • CocoaPods version 1.10.1

[✓] Chrome - develop for the web
    • Chrome at /Applications/Google Chrome.app/Contents/MacOS/Google Chrome

[✓] Android Studio (version 4.0)
    • Android Studio at /Applications/Android Studio.app/Contents
    • Flutter plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/9212-flutter
    • Dart plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/6351-dart
    • Java version OpenJDK Runtime Environment (build 1.8.0_242-release-1644-b3-6222593)

[✓] VS Code (version 1.55.0)
    • VS Code at /Applications/Visual Studio Code.app/Contents
    • Flutter extension version 3.22.0

[✓] Connected device (1 available)
    • Chrome (web) • chrome • web-javascript • Google Chrome 90.0.4430.212

• No issues found!
```
这样就安装成功了。

#### 5.2 更新CocoaPods

[更新 CocoaPods 查看](https://github.com/matiastang/cocoaPads/blob/master/md/cocoaPads%E5%AE%89%E8%A3%85.md)
1. 查看版本`pod --version`
```
# 查看版本
pod --version
Ignoring ffi-1.13.1 because its extensions are not built. Try: gem pristine ffi --version 1.13.1
1.9.3
# 查看ruby源（默认为https://rubygems.org/国内使用https://gems.ruby-china.org）
gem sources -l
Ignoring ffi-1.13.1 because its extensions are not built. Try: gem pristine ffi --version 1.13.1
*** CURRENT SOURCES ***

https://gems.ruby-china.com
# 查看ruby版本
gem -v
Ignoring ffi-1.13.1 because its extensions are not built. Try: gem pristine ffi --version 1.13.1
3.0.3
# 更新
sudo gem update --system
Password:
Ignoring ffi-1.13.1 because its extensions are not built. Try: gem pristine ffi --version 1.13.1
Latest version already installed. Done.
# 查看ruby版本
gem -v
Ignoring ffi-1.13.1 because its extensions are not built. Try: gem pristine ffi --version 1.13.1
3.0.3
# 更新cocoapods
sudo gem install -n /usr/local/bin cocoapods
Ignoring ffi-1.13.1 because its extensions are not built. Try: gem pristine ffi --version 1.13.1
Fetching activesupport-5.2.6.gem
Fetching public_suffix-4.0.6.gem
Fetching cocoapods-core-1.10.1.gem
Fetching cocoapods-downloader-1.4.0.gem
Fetching nanaimo-0.3.0.gem
Fetching addressable-2.7.0.gem
Fetching cocoapods-1.10.1.gem
Fetching xcodeproj-1.19.0.gem
Successfully installed activesupport-5.2.6
Successfully installed public_suffix-4.0.6
Successfully installed addressable-2.7.0
Successfully installed cocoapods-core-1.10.1
Successfully installed cocoapods-downloader-1.4.0
Successfully installed nanaimo-0.3.0
Successfully installed xcodeproj-1.19.0
Successfully installed cocoapods-1.10.1
Parsing documentation for activesupport-5.2.6
Installing ri documentation for activesupport-5.2.6
Parsing documentation for public_suffix-4.0.6
Installing ri documentation for public_suffix-4.0.6
Parsing documentation for addressable-2.7.0
Installing ri documentation for addressable-2.7.0
Parsing documentation for cocoapods-core-1.10.1
Installing ri documentation for cocoapods-core-1.10.1
Parsing documentation for cocoapods-downloader-1.4.0
Installing ri documentation for cocoapods-downloader-1.4.0
Parsing documentation for nanaimo-0.3.0
Installing ri documentation for nanaimo-0.3.0
Parsing documentation for xcodeproj-1.19.0
Installing ri documentation for xcodeproj-1.19.0
Parsing documentation for cocoapods-1.10.1
Installing ri documentation for cocoapods-1.10.1
Done installing documentation for activesupport, public_suffix, addressable, cocoapods-core, cocoapods-downloader, nanaimo, xcodeproj, cocoapods after 11 seconds
8 gems installed
# 查看cocoapods版本
pod --version
1.10.1
```
如上更新 `CocoaPods` 成功。

## 问题

### 使用过程中发现：flutter pub get时比较慢

参考[Community-run mirror sites](https://flutter.dev/community/china)，设置全局变量。

1. `vim ~/.zshrc `
2. 编辑并保持，如下替换为上海大学的源

```
# matiastang flutter

# export PUB_HOSTED_URL=https://pub.flutter-io.cn
# export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://mirrors.sjtug.sjtu.edu.cn/
export PUB_HOSTED_URL=https://dart-pub.mirrors.sjtug.sjtu.edu.cn/
```
3. `source ~/.zshrc`

效果很好，速度明显提升
```
$ flutter pub get
Running "flutter pub get" in matias_flutter_helloworld...           8.4s
```