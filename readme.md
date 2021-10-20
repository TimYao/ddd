学习lerna

lerna 作为一款多功能包管理工具，具有灵活管理多包，使得多包之间开发引用灵活

方法：

 - 在本地支持node环境下全局安装leran

 - 建立开发目录，在目录中lerna init 初始化lerna管理，注意的是在不加--independent参数下lerna会统一管理包版本，否则可灵活管理单个包

 - 对包添加命名管理，lerna create <packageName> --access public 保证包私作用域

 - 若在目录中添加workspaces配合yarn 完成对各包之间的软连接，并在lerna.json中设置useWorkSpaces:true开启

 - yarn install / lerna bootstrap开启包软连包到根

 - yarn link === npm link

发包：

 - 保证当前已登录到资源

 - 保证当前修改的内容已经提交至git仓库，由于lerna关联了git仓库，本地开发目录必须已经支持了git仓库的建立

 - 保证提交git仓库成功

 - lerna publish 发布包 

 - lerna publish from-git/from-package 保证再次提交，不更新package.json

整理：

 在lerna发布过程中会拿当前的本地包去和git远程仓库中包进行比对，找到对应的变更包进行版本更新然后再提交，这里要注意提交分支要统一，或者打tag带来的问题


