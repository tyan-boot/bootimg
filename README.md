﻿#boot.img操作

##联系我
邮箱:tyan-boot@outlook.com

##基本参数


*  __-u in\_file__   解压boot.img或recovery.img //已实现
*  __-r out\_file__   重新打包，out_file为输出文件  //已实现

##使用-u命令会创建如下文件
*  _config_   配置文件，内部记录一些打包所需数据
*  _kernel_   内核部分
*  _ramdisk.gz_  使用gzip压缩的内存盘，解压后得到ramdisk文件，通常是CPIO档案
*  _second\_stage_  此部分绝大多数情况下为0
  
##使用-r命令会读取上述四个文件进行打包
  除second_stage不是必须之外，其余三个文件必须同时存在，否则无法进行打包
  
  
##注意
如果你发现使用-u解包的文件再次使用-r打包之后文件大小不一样，请不用担心，通常是文件结尾部分不一样，原文件结尾可能有一些空白数据，但重新打包之后是不包含空白数据的，但这不影响使用:)

##计划中内容
* 整合GZIP以及CPIO