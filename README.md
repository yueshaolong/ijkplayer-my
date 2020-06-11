# kgplayer
基于IjkPlayer 0.8.3版本封装的基础播放器，支持http,rtsp,rtmp

# 第一种方案
在kgplayer模块的build.gradle文件中，加入如下：
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation "androidx.appcompat:appcompat:1.1.0"
    //引入jar使用相关api
    api "tv.danmaku.ijk.media:ijkplayer-java:$rootProject.ijkPlayerVersion"
    //引入so文件，相当于在文件夹libs/armeabi-v7a/下面放入需要的so文件
   implementation "tv.danmaku.ijk.media:ijkplayer-armv7a:$rootProject.ijkPlayerVersion"
}
优点：简单便捷；但测试支持http,rtmp格式的视频流；不支持rtsp格式视频

# 第二种方案
下载源码并自己修改配置，并编译好so库引用即可；
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation "androidx.appcompat:appcompat:1.1.0"
    //引入jar使用相关api
    api "tv.danmaku.ijk.media:ijkplayer-java:$rootProject.ijkPlayerVersion"
    //引入so文件，相当于在文件夹libs/armeabi-v7a/下面放入需要的so文件
//   implementation "tv.danmaku.ijk.media:ijkplayer-armv7a:$rootProject.ijkPlayerVersion"
}
在目录kgplayer-java/src/main/下添加jniLibs,并添加so库文件。

# 注意我这里的so库版本是0.8.3，所以依赖中ijkplayer-java的版本也要改为0.8.3


