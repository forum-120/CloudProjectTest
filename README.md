# CloudProjectTest
使用云服务器搭建服务器，利用nodejs和next.js框架写了最基本的demo
这里记录一下过程
首先上云服务网站购买服务器，我在腾讯云购买了最便宜的服务。然后安装镜像，安装完ubuntu系统后安装nodejs next.js等。
安装完成后首先试了自己写的最简单的demo，开启服务后成功运行
然后去试了用nextjs框架，这里就出问题了
首先按照nextjs官网步骤安装nextjs，使用npm run dev时出错：

<img width="692" alt="image" src="https://user-images.githubusercontent.com/71775813/190836616-7952b3f5-9299-4a8f-81f4-0cbc8986d2d3.png">
这是因为nodejs版本太低的问题，之后安装n命令，使用n stable升级版本，然而升级版本却失败，无法让nodejs更换到最新版本
这是因为nodejs安装在/usr/local/bin/node中，而n安装在/usr/local/bin中，使用n安装的nodejs也在/usr/local/bin中，故无法使用n切换版本
这里作如下操作：rm -rf /usr/local/bin/node 删除了原路径，则可以正常使用最近用n安装的nodejs
然后使用hash -r，则发现已经切换到最新版本

<img width="1134" alt="image" src="https://user-images.githubusercontent.com/71775813/190836923-81ba81f2-a118-4a35-b927-91328fa52ed1.png">


之后再使用npm run dev，则开启服务成功




