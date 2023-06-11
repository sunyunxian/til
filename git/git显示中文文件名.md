# git 显示中文文件名

## 问题

git status 的时候中文文件名不显示中文

## 解决

`git config --global core.quotepath false` 设置这个配置之后会把中文进行转义，只要终端支持中文就是可以正常显示了。
