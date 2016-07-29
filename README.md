# shtml
shtml入门个人总结
shtml和asp 有一些相似，以shtml命名的文件里，使用了ssi的一些指令，就像asp中的指令，你可以在SHTML文件中写入SSI指令，
当客户端访问这些shtml文件时， 服务器端会把这些SHTML文件进行读取和解释。


主要有以下几种用用途： 
1、显示服务器端环境变量<#echo> 
2、将文本内容直接插入到文档中<#include> 
3、显示WEB文档相关信息<#flastmod><#fsize>(如文件制作日期/大小等) 
4、直接执行服务器上的各种程序<#exec>(如CGI或其他可执行程序) 
5、设置SSI信息显示格式<#config>(如文件制作日期/大小显示方式) 
高级SSI<XSSI>可设置变量使用if条件语句。

SSI是为WEB服务器提供的一套命令，这些命令只要直接嵌入到HTML文档的注释内容之中即可。如： 
<#include file="info.htm"--> 
就是一条SSI指令，其作用是将"info.htm"的内容拷贝到当前的页面中，当访问者来浏览时，会看到其它HTML文档一样显示info.htm其中的内容。
参数： 
file 指定包含文件相对于本文档的位置 如 info.txt 表示当前目录下的的info.txt文档 
virtual 指定相对于服务器文档根目录的位置 如 /hoyi/info.txt 表示 

#exec 示范 
作用： 
将某一外部程序的输出插入到页面中。可插入CGI程序或者是常规应用程序的输入，这取决于使用的参数是cmd还是cgi。 
语法： 
程序代码: 
<!--#exec cmd="文件名称"--> 
<!--#exec cgi="文件名称"--> 
<!--#exec cmd="文件名称"--> 
<!--#exec cgi="文件名称"--> 
参数： 
cmd 常规应用程序 
cgi CGI脚本程序 
禁止方法： 
1.Apache，将access.conf中的"Options Includes ExecCGI"这行代码删除； 
2.在IIS中，要禁用 #exec 命令，可修改 SSIExecDisable 元数据库； 
