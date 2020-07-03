
#### 如果图片没有展示出来,建议clone到本地用macdown编译器打开README.md


## 准备

[FlutterSDK下载](https://flutter.io/docs/development/tools/sdk/archive?tab=macos#macos) 

[Java环境](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) 选择 **Mac OS X x64** 同意协议后可下载安装包

[Android Studio](https://developer.android.com/) 下载最新版本

[vs code](https://code.visualstudio.com) 下载最新版本(可选)

## 配置Flutter环境变量

将下载好的`flutter`文件夹拖到任意位置中(我是拖到mac根目录下，所以我的路径是/Users/mac/flutter)，然后在找到下载好的`fultter`文件夹拖到命令行中得到`flutter文件夹`路径。

![Untitled.png](https://upload-images.jianshu.io/upload_images/1419035-bbe1ab49153fa7fb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在终端执行

```dart
open .bash_profile
```

如果没有.bash_profile,那么创建一个

```dart
cd ~

touch .bash_profile

open .bash_profile
```

依次将这三句话复制加进去

```dart
export PUB_HOSTED_URL=[https://pub.flutter-io.cn](https://pub.flutter-io.cn/)
export FLUTTER_STORAGE_BASE_URL=[https://storage.flutter-io.cn](https://storage.flutter-io.cn/)
export PATH=/路径/bin:$PATH
```

关闭保存,打开终端输入

```json
source ~/.bash_profile
```

完成后,验证是否安装成功

```json
flutter -h
```

出现如下结果代表安装顺利

![https://upload-images.jianshu.io/upload_images/1419035-5dd39fb9769f6624.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240](https://upload-images.jianshu.io/upload_images/1419035-5dd39fb9769f6624.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果输入flutter命令卡主不动，请多等一会试试

## 安装Android Studio

### 配置java环境

首先运行前面下载好的`JDK`环，一直下一步直到安装完成

### 安装Android Studio

安装教程[Android Studio](https://www.cnblogs.com/xiadewang/p/7820377.html)

### 安装插件Flutter和Dart

打开`Android Stuido` 软件，然后找到`Plugin`的配置，搜索`Flutter`插件,搜索`flutter`,点击右侧`install`,完成后重启,

加载不出来就开下vpn试试.

![Untitled1.png](https://upload-images.jianshu.io/upload_images/1419035-90ae96f110a6e339.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![Untitled2.png](https://upload-images.jianshu.io/upload_images/1419035-b290380b503fbf4f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

安装结束后在命令行输入如下命令，全部输入`y`

```json
flutter doctor --android-licenses
```

## 安装CocoaPod

### 配置`brew`

下面依次输入到终端

```json
brew install --HEAD libimobiledevice

brew install ideviceinstaller

brew install ios-deploy

brew install cocoapods

pod setup
```

如果安装失败执行

```json
/usr/bin/ruby -e "$(curl -fsSL [https://raw.githubusercontent.com/Homebrew/install/master/install](https://raw.githubusercontent.com/Homebrew/install/master/install))"
```

一次不行,就多试几次

```json
brew update

brew uninstall --ignore-dependencies libimobiledevice

brew uninstall --ignore-dependencies usbmuxd

brew install --HEAD usbmuxd

brew unlink usbmuxd

brew link usbmuxd

brew install --HEAD libimobiledevice

brew install ideviceinstaller
```

## 安装VSCode(可选)

直接点击安装包安装，按照提示一直下一步即可

### 配置Dart环境变量

如果需要在`vscode`中运行`Dart` 项目，还需要配置`Dart`的环境变量

目前在终端输入`dart` 终端输出

```dart
dart: command not found
```

在终端输入

```dart
open .bash_profile
```

将根据自己的`flutter`路径添加下面两行代码

```dart
//  export DART_HOME=/dart-sdk/bin 路径
export DART_HOME=/Users/mac/flutter/bin/cache/dart-sdk/bin
export PATH="${DART_HOME}:${PATH}"
```

关闭保存

```dart
source ~/.bash_profile
```

测试是否安装成功，在终端输入`dart`

```dart
Usage: dart [<vm-flags>] <dart-script-file> [<script-arguments>]

Executes the Dart script <dart-script-file> with the given list of <script-arguments>.

Common VM flags:
--enable-asserts
  Enable assert statements.
--help or -h
  Display this message (add -v or --verbose for information about
  all VM options).
--package-root=<path> or -p<path>
  Where to find packages, that is, "package:..." imports.
--packages=<path>
  Where to find a package spec file.
--observe[=<port>[/<bind-address>]]
  The observe flag is a convenience flag used to run a program with a
  set of options which are often useful for debugging under Observatory.
  These options are currently:
      --enable-vm-service[=<port>[/<bind-address>]]
      --pause-isolates-on-exit
      --pause-isolates-on-unhandled-exceptions
      --warn-on-pause-with-no-debugger
  This set is subject to change.
  Please see these options (--help --verbose) for further documentation.
--write-service-info=<file_name>
  Outputs information necessary to connect to the VM service to the
  specified file in JSON format. Useful for clients which are unable to
  listen to stdout for the Observatory listening message.
--snapshot-kind=<snapshot_kind>
--snapshot=<file_name>
  These snapshot options are used to generate a snapshot of the loaded
  Dart script:
    <snapshot-kind> controls the kind of snapshot, it could be
                    kernel(default) or app-jit
    <file_name> specifies the file into which the snapshot is written
--version
  Print the VM version.
```

终端删除如上代表配置成功

来到`vscode`，在终端输入`dart`，发现还是

```dart
dart: command not found
```

打开`vscode`将终端的类型设置为`bash`,重启`vscode`

同样在命令行输入`dart`

![1.jpg](https://upload-images.jianshu.io/upload_images/1419035-71277d5fc606152e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 验证安装是否成功

执行命令

```dart
flutter doctor
```

如果所有选项都是对号代表环境配置成功，否则按照提示修复对应问题。

新建一个项目

```dart
flutter create project_name
```

在命令行模式输入`flutter run`会自动启动模拟器

![https://upload-images.jianshu.io/upload_images/1419035-5482d4188f2ab43c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240](https://upload-images.jianshu.io/upload_images/1419035-5482d4188f2ab43c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### **其他**

VSCode可能需要安装的插件

`Awesome Flutter Snippets`快捷生成代码插件

`path`快速引入文件路径

`Code Runner`

`Chinese (Simplified) Language Pack for Visual Studio Code` 菜单汉化

**常用的快捷键**

运行项目 `flutter run`

创建项目 `flutter create xxx`

`vscode`格式化代码 `option + f + shift`

在`vscode`中的命令行模式下

r 键：点击后热加载，也就算是重新加载吧。

p 键：显示网格，这个可以看到App布局情况。

o 键：切换`android`和`ios`的预览模式。

q 键：退出调试预览模式。

**tips**

当鼠标悬停到`Widget`的时候，可以看到这个`Widget`都有哪些属性，

**代码规范**

`fluttet`严格区分大小写,项目名称必须是小写

[回到顶部](https://www.notion.so/bc715740a81943c8a4d9fcf990e7f55a#93a8c61fac3e49a3ad46ee98f5caf3ed)