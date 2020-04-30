flutter学习网址汇总

flutter中文网：https://flutterchina.club/get-started/install/

json转dart数据模型的一个工具

https://javiercbk.github.io/json_to_dart/

Flutter实战视频-移动电商 （第69节更新）

https://www.jspang.com/detailed?id=53

Mac下查看已安装的jdk版本及其安装路径

打开终端，输入：/usr/libexec/java_home -V（注意：输入命令参数区分大小写(-v是不对的，必须是大写-V)）

flutter功能调研
1、分享到其他app
flutter 跳转到其他APP的两种方式
方法1:使用url_launcher:
第一步:pubspec.yaml 添加 url_launcher: ^5.0.3
第二步 package get
第三步 import 'package:url_launcher/url_launcher.dart';
第四步 代码
if (await canLaunch(url)) {
      await launch(url);
    } else {
      throw 'Could not launch $url';
    }
//URL是一个字符串  一般是 scheme + host
但是我在使用这个方法的时候有部分APP使用不了 可能是这些APP的主页面没有设置scheme和host吧 所以我使用了下面这种方式

方法2:使用linker
第一步:pubspec.yaml 添加 linker: 0.0.2
第二步 package get
第三步 import 'package:linker/linker.dart';
第四步 代码
if (Platform.isAndroid) {//判断是否是android平台
      try {
        await Linker.startActivity(new Intent.callApp(packageName: 包名,className: activity的绝对路径));
      } on PlatformException catch (e) {
        print("Open failed $e");
      }
    }
这种方法是通过报名打开的 同时也支持iOS 但是不是用报名（iOS没有包名不是） 下面我会继续写打开公众号 所以以后会更新

作者：雪纳瑞的哈士奇
链接：https://www.jianshu.com/p/6867b6414b7a
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
