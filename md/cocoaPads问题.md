# cocoaPads

## CDN: trunk URL couldn't be downloaded: https://cdn.cocoapods.org/all_pods_versions_8_a_0.txt Response: Couldn't connect to server

version: 1.9.1

执行：
```
pod search **
```
提示： CDN: trunk URL couldn't be downloaded: https://cdn.cocoapods.org/all_pods_versions_8_a_0.txt Response: Couldn't connect to server

[官方文档](http://blog.cocoapods.org/CocoaPods-1.8.0-beta/)
[github issues](https://github.com/CocoaPods/CocoaPods/issues/9303)

```
$ pod repo list                                         

aliyun
- Type: git (master)
- URL:  https://github.com/aliyun/aliyun-specs.git
- Path: /Users/yunxi/.cocoapods/repos/aliyun

cocoapods
- Type: git (unknown)
- URL:  https://github.com/CocoaPods/Specs.git
- Path: /Users/yunxi/.cocoapods/repos/cocoapods

trunk
- Type: CDN
- URL:  https://cdn.cocoapods.org/
- Path: /Users/yunxi/.cocoapods/repos/trunk

3 repos
```
`podfile`文件中一定要指定`master`源，因为现在默认是`trunk`源
在`Podfile`中添加`source`源：
```
source 'https://github.com/CocoaPods/Specs.git'
```
`podfile`文件中添加source源后，`pod install`和`pod update`可以正常操作。
但是`pod search`有些库却不正常,此时可以在终端执行：
```
pod repo remove trunk
```