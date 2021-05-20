<!--
 * @Author: tangdaoyong
 * @Date: 2021-05-20 10:19:11
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-05-20 10:29:40
 * @Description: Flutter 升级
-->
# Flutter 升级

[Flutter 升级](https://flutterchina.club/upgrading/)

## 查看分支

$ `flutter channel`
```
flutter channel
Flutter channels:
* master
  dev
  beta
  stable
```

## 切换分支


切换到稳定版本：`flutter channel stable`

```
flutter channel stable
Switching to flutter channel 'stable'...
git: Switched to a new branch 'stable'
git: Branch 'stable' set up to track remote branch 'stable' from 'origin'.
Successfully switched to flutter channel 'stable'.
To ensure that you're on the latest build from this channel, run 'flutter upgrade'
```
使用`flutter channel`查看时，会更新依赖。
```
flutter channel       
Downloading Dart SDK from Flutter engine a9d88a4d182bdae23e3a4989abfb7ea25954aad1...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  200M  100  200M    0     0  1143k      0  0:02:59  0:02:59 --:--:-- 1171k
Building flutter tool...
Flutter assets will be downloaded from https://storage.flutter-io.cn. Make sure you trust this source!
Downloading package sky_engine...                                1,222ms
Downloading flutter_patched_sdk tools...                            5.0s
Downloading flutter_patched_sdk_product tools...                 2,858ms
Downloading darwin-x64 tools...                                    66.6s
Downloading darwin-x64/font-subset tools...                         5.3s
Flutter channels:
  master
  dev
  beta
* stable
```

## 升级 Flutter channel 和 packages

要同时更新`Flutter SDK`和你的依赖包，在你的应用程序根目录（包含`pubspec.yaml`文件的目录）中运行`flutter upgrade` 命令:

$ `flutter upgrade`
