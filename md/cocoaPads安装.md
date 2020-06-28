# cocoaPads安装

[参考](https://www.jianshu.com/p/adad5ee721af)
[cocoaPods源更换](https://www.jianshu.com/p/68a3bc2a41fc)
[清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/)
[gitHub cocoapods](https://github.com/CocoaPods/Specs)
[参考](https://zhuanlan.zhihu.com/p/64732905)
## 安装

1. cocoaPads安装

gem sources -l //查看ruby源（默认为https://rubygems.org/）
gem source -a https://gems.ruby-china.org
输入gem sources -l      　　　　　　  //检测是否成功
结果为https://gems.ruby-china.org      //则成功

升级Gem.
Gem是来管理Ruby标准包.
sudo gem update --system　  //升级gem

gem -v 　　　　　　　　　　　　//查看版本

安装CocoaPods
sudo gem install cocoapods　　  // Mac OS X 10.11前  输入这一条
sudo gem install -n /usr/local/bin cocoapods  //Mac OS X 10.11后   输入这一条
pod setup   
pod --version       //查看版本

2. cocoaPads换源

[清华开源，CocoaPods 镜像使用帮助](https://mirrors.tuna.tsinghua.edu.cn/help/CocoaPods/)

对于旧版的 CocoaPods 可以使用如下方法使用 tuna 的镜像：
```
$ pod repo remove master
$ pod repo add master https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git
$ pod setup  // 下载代码成功后执行 
$ pod repo update
```

新版的 CocoaPods 不允许用pod repo add直接添加master库了，但是依然可以：
```
$ cd ~/.cocoapods/repos
$ pod repo remove master
$ git clone https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git master
```

最后进入自己的工程，在自己工程的podFile第一行加上：
```
$ source 'https://mirrors.tuna.tsinghua.edu.cn/git/CocoaPods/Specs.git'
```

pod install --verbose --no-repo-update //不去更新repo