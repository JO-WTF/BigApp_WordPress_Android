# BigApp_WordPress_Android

##1. 网站端事项

###A. 安装WP-BigApp插件
>>Wordpress -> 管理站点 -> 仪表盘 -> 插件 -> 安装插件 -> 搜索bigapp，点击WP-BigApp安装即可

###B. 安装Avatar插件（可选，客户端用户头像上传和显示功能所需，本demo使用的WP User Avatar）
>>Avatar插件中相关设置如下:

![](https://raw.githubusercontent.com/BigAppOS/BigApp_WordPress_Android/master/screenshots/1.png)
      

##2. Android客户端配置项说明（请确保网站已安装bigapp插件）
    
    （注意：请使用Android Studio开发工具， gradle脚本编译）

###A. needs_files目录
>>这个目录下面主要是app的一些配置信息，主要关注下面文件：
####a. ic_launcher_xx.png 代表的是您应用各种尺寸的icon。
####b. ShareSDK.xml 本app使用的是sharesdk第三方分享，请拷贝QQ、sina、微信开发者平台的key到此文件中。
####c. demokey.keystore 文件是apk的签名文件，请替换成您的签名文件
>>（注意：如果修改了签名文件的名称，还需要修改app/build.gralde文件中的值"../needs_files/demokey.keystore"）
####d. params.xml app功能配置信息（见params.xml里面注释）
（注意：以下配置仅在编译release版本下全部有效；debug版本下仅部分配置有效，未生效的均采用默认配）
>>
    <Asset>
        <!-- nav bar的颜色 -->
        <nav_color>#FFFFFF</nav_color>
        <!-- app的名称 -->
        <app_name>bigApp</app_name>
        <!-- app的包名 -->
        <package_name>com.youzu.wp.bigword</package_name>
        <!-- 版本号 -->
        <version_name>1.0.1</version_name>
        <version_code>101</version_code>
        <svn_version>6719</svn_version>
        <!-- 您的站点地址 -->
        <api_url>http://wp.bigappdemo.com/</api_url>
        <!-- keystore 相关信息 -->
        <store_pwd>123456</store_pwd>
        <key_alias>demokey.keystore</key_alias>
        <key_pwd>123456</key_pwd>
        <!-- 使用QQ分享时用到的app_id-->
        <qq_app_id>1104849854</qq_app_id>
        <!-- 分享到qq、sina、微信;1代表启用，0代表不启用-->
        <use_qq>1</use_qq>
        <use_sina>1</use_sina>
        <use_wechat>1</use_wechat>  
    </Asset>
    
###B. outputs目录
>>当执行gralde assembleRelease后会生成对应的release版本apk到此目录下面
