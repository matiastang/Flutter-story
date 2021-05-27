<!--
 * @Author: tangdaoyong
 * @Date: 2021-05-21 10:38:29
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-05-27 09:38:44
 * @Description: Flutter开发Packages和plugin
-->
# Flutter开发Packages和plugin

[flutter 包搜索](https://pub.flutter-io.cn/packages)
[flutter 插件官网](https://pub.dartlang.org)
[使用 Flutter package](https://flutter.cn/docs/development/packages-and-plugins/using-packages)

## 介绍

`Flutter`三方的工具有两种

1. 一种是插件（`Plugin`）
> `Plugin`不仅包含了`Dart`代码，还包含了`iOS`以及安卓的原生代码，比如常用的`image_picker`。

2. 一种是包（`Package`）。
> `Package`就仅仅是`Dart`代码库。

Package 和插件 (plugin) 有什么区别呢？ 插件 (plugin) 是 package 的一种，全称是 plugin package，我们简称为 plugin，中文叫插件。

Packages
Dart package 最低要求是包含一个 pubspec.yaml 文件。此外，一个 package 可以包含依赖关系 (在 pubspec.yaml 文件里声明)、 Dart 库、应用、资源、测试、图片和例子等。 pub.dev 上列出了很多 package，由 Google 工程师和 Flutter 和 Dart 社区的开发者开发和发布，你可以用在自己的应用里。

Plugins
插件 (plugin package) 是一种特别的 package，特别指那些帮助你获得原生平台特性的 package。插件可以为 Android (使用 Kotlin 或 Java 语言)、 iOS (使用 Swift 或 Objective-C 语言)、Web、macOS、Windows、Linux 平台，或其任意组合的平台编写。比如：某个插件可以为 Flutter 应用提供使用原生平台的摄像头的功能。

## Package及Plugin开发命令

创建Dart包（package）
要创建Dart包，使用参数--template=package 来执行 flutter create

flutter create --template=package 'package_name'
创建插件（Plugin）
要创建插件包，请使用--template=plugin参数执行flutter create

flutter create --template=plugin 'plugin_name'
指定组织名称
使用--org选项指定你的组织，并使用反向域名表示法。

Dart包package是不需要组织名称的，--org只有在 --template=plugin时才生效。

flutter create --org com.example --template=plugin 'plugin_name'
指定其他语言
由于Plugin包含iOS和Android代码，而他们分别都支持两种语言，iOS支持Object-C（默认）和Swift，Android支持Java（默认）和Kotlin，所以我们可以使用-i 或 -a 为iOS或Android指定语言。

flutter create --template=plugin -i swift -a kotlin 'plugin_name'
发布Dart包
检查包
flutter packages pub publish --dry-run
发布
flutter packages pub publish
注意：目前发布插件和包都需要Google账号，同时需要翻墙。
当出现下面提示。此时需要你使用浏览器访问提示中的链接，用你的Google账号授权。


有时就算是拥有翻墙也并不能解决问题，因为我们还配置了相关的镜像。Flutter官方就建议过镜像的配置，所以我们在发布插件或者包的时候，就会因为镜像出现下面错误。


那么解决它的问题也很简单，就是指定服务器发布。

指定服务器发布

flutter packages pub publish --server=https://pub.dartlang.org