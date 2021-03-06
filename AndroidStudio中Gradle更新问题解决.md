# Gradle更新问题解决    
## 错误    
今天AndroidStudio 2.3.0发布了，好多小伙伴已经更新了，但是我更新后，打开项目就一直停在**refreshing gradle project**这个进程，项目也加载不出来。这种问题在软件更新后经常出现，有2种解决办法。   

## 解决(1)    
* 问题就出在Gradle身上，我们先查看一下出错的Gradle信息。   
  * 在左侧项目栏切换到project模式下，进入  
  **gradle**->**wrapper**->**gradle-wrapper.properties**,双击会出现如下界面    
  ![](http://p1.bqimg.com/567571/16948d4ee69a93c2.png)  
  问题出在最后一行，Gradle不能进入这个url所指的地址下载需要的gradle包。   
  PS：这里的地址是我修改过后的    
* 找到错误的包后，我们就去官网下载对应的gradle包      
   [链接在这里](http://services.gradle.org/distributions/)      
  * 将下载的包上传到网盘或者本地服务器，将gradle-wrapper.properties中的url改为这个下载地址  
  * 然后重启，问题就应该解决了。

## 解决(2)   
这个方法适用于出现下面的错误   
**Error: SSL peer shut down incorrectly**    
同样是因为gradle不能正确下载所需要gradle版本压缩包导致的。

* 同样翻墙进入Gradle官网：   
![](http://p1.bqimg.com/567571/110346e0589b652f.png)   
可以看到这时候最新的版本是3.4.1，并不推荐下载最新版本，可以选择稍微老的版本，这里我下载了3.3版本。    

* 将下载好的gradle包解压到AndroidStudio安装路径下的Gradle路径下，然后重启软件，gradle就会马上加载完成，你就可以愉快的进行你的项目了。   
