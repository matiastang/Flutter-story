<!--
 * @Author: tangdaoyong
 * @Date: 2021-05-20 14:54:58
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-05-20 15:04:03
 * @Description: 创建项目
-->
# 创建项目

[创建web项目](https://flutter.cn/docs/get-started/web)

## 创建一个空项目

```
flutter create myapp
```
*注意*项目名称只能包含`0-9a-z_`内的字母。

## 现在项目添加支持

```
flutter create .
```

## flutter devices

开启了 Web 支持，运行 flutter devices，命令会输出一个名为 Chrome 的设备信息，开启一个为 Web 应用提供服务的 Web Sever，并打开 Chrome 浏览器并访问某个 URL 地址。

## 开发

```
flutter run -d chrome
```

## build

```
flutter build web
```