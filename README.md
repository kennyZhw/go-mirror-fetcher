# go-mirror-fetcher
The bat for fetch go packages mirror

在国内，许多情况下无法直接通过go get获取到golang官网上的语言包，为了解决该问题，网上的解决方案是通过获取github上的镜像源码来解决该问题。因为考虑到每次进行链接的拼改显得格外麻烦，所以想着写一个脚本来处理一些重复繁琐的工作，所以就有了这个脚本，希望能为大家提供一点帮助。

使用说明：
1、把脚本clone到本地，然后双击bat脚本
2、根据提示输入GOPATH目录，需要是绝对路径
3、根据提示输入需要下载的镜像包名称
4、此时便会开始下载镜像包，下载成功后会存放在%GOPATH%\src\golang.org\x\目录下面
