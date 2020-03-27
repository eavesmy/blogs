#### 修改app名字
- android: ```android/app/src/main/AndroidManifest.xml``` 修改 ```label```。
- ios: ```ios/Runner/info.plist``` 修改 ```CFBundleName``` 字段。

#### 修改图标
- android: ```android/app/src/main/res``` 替换相同尺寸格式即可。
- ios: ```ios.Runner/Assets.xcassets/AppIcon.appiconset``` 同上。

#### 去掉右上角的 debug
``` MaterialApp``` 设置属性 ```debugShowCheckedModeBanner: false```

#### Webview 打开 https 页面报错
[webview_plugin解决方法](https://github.com/fluttercommunity/flutter_webview_plugin/issues/298)
[webview_flutter解决方法](https://blog.csdn.net/shifang07/article/details/95317258)

#### 项目启动不了
```Default activity not found```, 删除以下几个缓存文件
```
~/.gradle/cache
~/.AndroidStudio/system/caches
<project dir>/build
<project dir>/android/.gradle
```

#### dio 强行认证证书
[解决方法](https://pub.dev/packages/dio#https-certificate-verification), 记得引用这俩
```
import 'dart:io';
import 'package:dio/adapter.dart';
```
