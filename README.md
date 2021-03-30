# opms

一、go开发环境：
  安装完go，使用 go env命令查看  GOPATH环境变量的路径指向，比如：/home/go_temp
  
  那么go_temp下必须要有  src目录，bin目录，pkg目录。
  
  作用分别是：
   src下存放实际开发的项目，比如此项目，opms，就放在src下，src下可以放多个项目和github的三方库

   bin目录是存放src中编译后的可执行文件
       （生成可执行文件方法：在src下执行 go install opms 即可自动编译到bin目录下，报错无法编译成功，不要使用go build命令，会导致src下出现编译后的文件和未变异文件混淆的情况）

   pkg目录是存放.a的文件，一般情况下使用go install命令即可，此文件夹用不到





二、项目使用：
  opms项目目录放在src下
  本地开发完git提交源码（不提交编译后的可执行文件或二进制）
  git提交后到远程机器拉代码，拉完使用 一、 中说明的go install命令进行项目整体编译
  最终去执行bin下刚编译完的可执行文件（后台执行命令：nohup ./可执行文件 >>log.text 2>&1 &）
  没报错说明正常，完事。
