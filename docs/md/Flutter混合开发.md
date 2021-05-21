<!--
 * @Author: tangdaoyong
 * @Date: 2021-05-21 09:23:15
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-05-21 09:55:11
 * @Description: flutter混合开发
-->
# flutter混合开发

## 介绍

在已有项目接入`Flutter`有两种方式：

1. 官方的接入方式[将 Flutter 集成到现有应用](https://flutter.cn/docs/development/add-to-app)
2. 组件化的接入方式

主要介绍一下第二种组件接入的方式。

## 程序运行方式

程序的运行方式有两种

1. 静态编译（AOT：Ahead of Time）
静态编译的程序在执行前全部被翻译为机器码，通常将这种类型称为AOT （Ahead of time compiler）即 提前编译；如C、C++。
2. 动态解释（JIT：Just In Time）
动态解释则是一句一句边翻译边运行，通常将这种类型称为JIT（Just-in-time）即即时编译。如JavaScript、Python。
程序运行的方式和具体的语言没有强制关系，比如Python，既可以JIT，也可以AOT。

`Dart`同时支持两种方式，[Dart的JIT和AOT](https://github.com/matiastang/matias-Dart/blob/main/docs/md/Dart%20JIT%E5%92%8CAOT.md)

## 组件化的接入方式

## 编译输出

`flutter`使用如下命令可以直接生成编译产物。
```js
build ios-framework --cocopods --output="目标路径"
```