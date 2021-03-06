# iOS 开发工具链

以下链接需要处理：
1. [一条命令 快速配置 Xcode 各种 环境](https://my.oschina.net/u/727843/blog/731322)

### PNG压缩
    1. https://imageoptim.com/howto.html

### png尺寸检查
    1. http://blog.devtang.com/2012/08/26/use-script-to-power-up-ui-work/

### 脚本自动生成小尺寸的图片
    1. http://blog.devtang.com/2012/08/26/use-script-to-power-up-ui-work/
        > brew link jpeg, brew install imagemagick
    2. 同时推荐了：http://www.xnview.com/en/xnconvert/

### app icon 生成
    1. https://github.com/smallmuou/ios-icon-generator
    2. 包含android的，输入为1024：https://github.com/hibara/create-ios-all-icons-shellscript

### 搜索无用的图片
    1. https://github.com/examplecode/unused-image

### IOS压力测试工具
    1. http://my.oschina.net/u/147181/blog/193396, 相关的github地址：https://github.com/jonathanpenn/ui-auto-monkey

### 功能测试
    1. https://github.com/krukow/calabash-script

### 重新签名IPA
    1. https://github.com/nanonation/floatsign

### 脚本生成启动图
    1. https://github.com/danielpovlsen/ios-icons-launch-images-generator

### 编译脚本：（用于持续集成）
    1. [Jenkins+GitHub+fir_cli 一行命令从源码到fir.im](http://www.jianshu.com/p/0515e2465c49)

### 编译脚本 之 [nomad/shenzhen](https://github.com/nomad/shenzhen)

  * 可参考：[iOS持续部署平台（一）：SHENZHEN](http://blog.csdn.net/ljj_saver/article/details/47009723)

  * 血泪史
    1. gem install nokogiri的时候出错：参考[installing_nokogiri](http://www.nokogiri.org/tutorials/installing_nokogiri.html)

  * ipa build 执行的时候，因为各种参数，它依赖xcode配置，所以在project-schemaname-configurations-use xxx for command-line builds，这里对xxx的配置，决定了编译什么版本～

### 自动检查证书和配置文件的匹配性
    1. https://github.com/quadion/iOSValidation

### 脸书出品：https://github.com/facebook/xctool

    1. 参考[使用fastlane gym/xctool编写ipa打包脚本](http://www.jianshu.com/p/54ab07f2e63b)，使用xctool、gym编译iOS工程：
        > 简书讲两个脚本更新在：https://github.com/xilin/ios-build-script
        > gym：https://github.com/fastlane/fastlane
          > 1.How to set project path? GYM_PROJECT enviromental variable
        > xctool：https://github.com/facebook/xctool
        > fir：https://github.com/FIRHQ/fir-cli

        mark 一下，xcode 8下，貌似有点问题。。。暂时放在这里。

    2. 持续集成

        [使用fastlane实现iOS持续集成](http://blog.csdn.net/azhou_hui/article/details/51244667)

        mark 一下，xcode 8下，貌似有点问题。。。暂时放在这里。

### 编译脚本 之 

### check-signature，脚本

### [imagemagick 强大的图像处理库]()

[使用说明](http://www.charry.org/docs/linux/ImageMagick/ImageMagick.html)

安装 imagemagick：
brew install imagemagick

[安装 bew](http://webmedia.blog.163.com/blog/static/416695020123261226695/)
```
cd /usr/local
sudo mkdir homebrew
curl -L https://github.com/mxcl/homebrew/tarball/master | sudo tar xz --strip 1 -C homebrew
cd homebrew/bin
./brew -v
file brew
cat brew | moresudo ./brew update

...

如果~下没有文件".bash_profile" 请执行： touch '.bash_profile'

...

vim '.bash_profile'加入
export PATH=$PATH:/usr/local/homebrew/bin
```

### [清理 iOS 项目不用的图片资源](http://www.cocoachina.com/ios/20160531/16536.html)

  1. 图片调用方法：1. [UIImage imageNamed:@"image"], 2. <imageview image="image" id="rb9-sl-eqm"></imageview image="image" id="rb9-sl-eqm">, 3. 用法较少，就是名称中有固定编码的，比如"320x480"/"1080x720"，然后根据屏幕适配；又比如"-1"/"-2",数组方式使用的。

  [https://github.com/jjz/script/blob/master/un_used.py](https://github.com/jjz/script/blob/master/un_used.py)

  2. 该仓库下还可以使用：unused-image.sh, 使用方法：
  This shell script is used to check and clean unused image file in your project  directory，supoort Android and IOS.
  * show unused image file
      ```
      ./unused-image.sh -p /path/of/your/project
      ```
  * show and clean unused image file
      ```
      ./unused-image.sh -r -p /path/of/your/project
      ```

### 搜索文件

搜索文件的方式可以使用grep,ack都是不错的工具，但是有一种更快，更好的搜索文件内容的方式:The Silver Searcher，项目地址：https://github.com/ggreer/the_silver_searcher，The Silver Searcher使用方便，更快，更简单。

安装The Silver Searcher:
```
brew install the_silver_searcher
```

使用ag搜索, 搜索该目录下以及其子目录下的所有包括image的文件:
```
ag “image” ‘./’
```

### plist cli编辑工具：PlistBuddy

[PlistBuddy](http://blog.csdn.net/a351945755/article/details/46561249)

### 网速模拟工具

[Hardware IO Tools for Xcode, Network Linker Conditioner](http://www.cnblogs.com/qiyer/p/5363983.html), Xcode - Open Develop Tools - More Tools ^_^

### icons图标 <---> XXXX.iconset文件夹

[官方文档](https://developer.apple.com/library/content/documentation/GraphicsAnimation/Conceptual/HighResolutionOSX/Optimizing/Optimizing.html#//apple_ref/doc/uid/TP40012302-CH7-SW8)

将 文件夹名为XXXX.iconset的文件夹(包含若干个png图片) 打包成XXXX.icns文件：[使用这个命令， 我遇到 'Iconset contains no image resources.'，这个文章提到](https://blog.macsales.com/28492-create-your-own-custom-icons-in-10-7-5-or-later)
```
To convert a set of icons to an icns file:
iconutil -c icns <iconset filename>
```

将XXX.icns文件 转成 包含若干个png图片的文件夹：
```
To convert an icns file to a set of icons:
iconutil -c iconset <icns filename>
```

## [OCLint 静态代码分析工具](用OCLint给iOS代码做静态分析)

0. 需求

主要针对c,c++和Objective-c的静态分析

1. 安装

[OCLint](http://oclint.org/%E3%80%82)

2. Homebrew安装

安装第三方依赖
```
brew tap oclint/formulae
```
安装OCLint
```
brew install oclint
```
更新OCLint
```
brew update
brew upgrade oclint
```

### XCode日志分析

xcpretty命令分析日志信息, xcpretty是用来格式化xcodebuild输出的工具，使用ruby开发

1. 安装

[xcpretty](https://github.com/supermarin/xcpretty)

```
gem install xcpretty
```

### xctool 使用 OCLint ,配合jenkins 生成PMD 报告脚本


### 替换图标的示例脚本：

```
#! /bin/bash
# created by Ficow Shen

useDebugIcon(){

    rm -rf 项目根目录/Images.xcassets/AppIcon.appiconset || exit
    cp -r AutoPack/IconOfDebug/AppIcon.appiconset/ 项目根目录/Images.xcassets/AppIcon.appiconset || exit

    echo '* 已更改AppIcon 为：测试版 图标'
}
useReleaseIcon(){
    
    rm -rf 项目根目录/Images.xcassets/AppIcon.appiconset || exit
    cp -r AutoPack/IconOfRelease/AppIcon.appiconset/ 项目根目录/Images.xcassets/AppIcon.appiconset || exit
    
    echo '* 已更改AppIcon 为：正式版 图标'
}

echo 'changeAppIcon.sh 加载完毕！'
```

### 替换BundleID的示例脚本：

```
#! /bin/bash
# created by Ficow Shen

useDebugBundleID(){
    cd 项目根目录.xcodeproj/
    # sed -i 直接修改源文件，'' 备份文件名, 's/要被取代的字串/新的字串/g', 需要设置bundleID的文件
    # 假设com.a.a是测试环境使用的，com.b.b是正式环境使用的
    sed -i '' 's/com.a.a/com.b.b/g' project.pbxproj || exit
    cd ..
    echo '* 已更改bundle ID 为：com.b.b'
}
useReleaseBundleID(){
    cd 项目根目录.xcodeproj/
    sed -i '' 's/com.b.b/com.a.a/g' project.pbxproj || exit
    cd ..
    echo '* 已更改bundle ID 为：com.a.a'
}

echo 'editBundleID.sh 加载完毕！'
```
