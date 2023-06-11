# git根据不同目录使用不同的配置文件

git 2.13 可以分别配置子目录的配置。

## 目的

每个人有个人和公司的项目，就会导致提交的时候存在个人信息错乱的情况，这个时候使用不同的目录配置不同的配置是最好的。

## 方法

个人的全局配置在 `~/.gitconfig` 文件中，在这里面配置一个 `includeIf` 选项即可，这个选项会配置对应的目录和这个目录的配置文件

```git
# .gitconfig

[user]
    name = user_name
    email = email@persoon.com

[includeIf "gitdir:Users/sunyunxian/workspace/company/xyz/"]
    path = .gitconfig.foo
```

```git
# .gitconfig.foo

[user]
    name = user_name
    email = email@company.com
```
