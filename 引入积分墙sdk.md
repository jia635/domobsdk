[~~~~[](http://mobi.domob.cn/developer/sdk](http://mobi.domob.cn/developer/sdk)~~~~)### 引入积分墙SDK

如果您单纯是想体积分墙功能的功能，建议直接跳过这一步。直接[下载Demo](https://www.pgyer.com/domobwalldemo)

#### Step1.1 <b style='color:red'>Android Studio</b>集成

##### Step1.1.1 配置maven仓库地址
```java
repositories {
maven { url "https://raw.githubusercontent.com/jia635/domobwallsdk/master" }
}
```

在需要的项目Model中的build.gradle中配置，repositories和dependencies同一等级

##### Step1.1.2 依赖积分墙SDK
```java

dependencies {
  compile 'cn.dow:aowsdk:4.6.0'
}
```

在需要配置的Model 的build.gradle 中添加依赖SDK地址

##### <b style='color:red'>**其他方法：**</b>

下载Eclipse方法中的SDK，然后放到lib目录下导入Model项目

#### Step1.3 <b style='color:red'>Eclipse</b>集成

##### Step1.3.1 下载SDK

如果您已经有了多盟APPID，请先[下载SDK](http://s.domob.cn/sdk/domob_android_offerwall_sdk-4.3.0.zip)。SDK下载后解压，得到以下内容：

![](/assets/2222.png)

**目录说明：**

1、libs目录包含SDK。
2、AOWDataSDKSample是Eclipse环境下的Demo
3、aowdatasdksample是Android Studio环境下的Model形式的Demo,以Jar形式集成SDK
4、mavensdktest是Android Studio环境下的Model形式的Demo,以Maven形式集成SDK
5、AndroidManifest.xml包含了集成SDK所需的权限和Android组件的声明。

##### 



