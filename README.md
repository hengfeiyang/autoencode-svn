# 自动编码 for SVN

该程序会从指定的源SVN读取数据，实时将记录同步到新的SVN上。在同步的过程中，可以执行指定的处理。目前，已内置的处理有：

1. ZendGuard加密php
2. UglifyJS加密js
3. 压缩CSS

并能与源SVN保持一致的提交记录(svn log)，以方便管理和查看。

**安装：**

直接从svn中检出源代码：

```
svn co http://repos.9466.dev/go-autoencode-svn
cd go-autoencode-svn
go build
```

编译即可得到主程序。

配置文件示例：

1. acs.conf 主配置文件，主要指定来源SVN和目标SVN，以及相关依赖的路径，mail通知设置。
2. exclude.conf 辅助配置文件，在处理的过程中，如果某些文件不需要处理，可指定跳过。

**依赖：**

该程序依赖几个系统的东西：

1. subversion命令，svn处理使用
2. node和uglify模块，混淆JS使用
3. ZendGaurd，加密php使用

依赖的东东，需要提前安装好，然后在配置文件 acs.conf 中指定。

