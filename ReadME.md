# 团队开发管理规范

[1、代码编写规范](#一代码编写规范)

[2、使用git进行代码版本管理](#二使用git进行代码版本管理)

[3、开发任务记录在TAPD上面](#)

[4、每天早上举行一个5~10分钟的站会](#三站会)

[5、code review](#四code-review)

[6、周学习分享会](#五周学习分享会)


## 一、代码编写规范

### Python代码编写规范

1、Python代码规范遵循PEP8标准。

2、命名规则：
- 类采用大驼峰命名法，比如：DebugFilesKeyError、UnexpectedUnicodeError。
- 方法和函数和变量命名采用下划线命名法，比如：attach_enctype_error_multidict。
- 保护的成员以单个下划线作为前缀，混合类则使用双下划线。

3、统一使用 4 个空格进行缩进。

4、所有的方法和类需要编写详细注释。

5、单元测试：
- 条件覆盖：设计足够的测试用例，运行所测程序，使程序中每个判断的每个条件的每个可能取值至少执行一次。
- 判定覆盖：设计若干个测试用例，运行所测程序，使程序中每个判断的取真分支和取假分支至少执行一次。
- 原则上一条验收标准可以对应至少一个断言（assert），没有断言的测试被视为无效测试；
具体可以参考：https://github.com/divio/django-cms/tree/develop/cms/tests

### JavaScript编码规范

1、遵循ESLint格式编写要求

2、[变量方法命名规范](http://alloyteam.github.io/CodeGuide/)

3、[Vue命名规范](./vue编码规范.md)

## 二、使用git进行代码版本管理 

前面讲到版本库的两条主要分支：Master和Develop。前者用于正式发布，后者用于日常开发。其实，常设分支只需要这两条就够了，不需要其他了。
但是，除了常设分支以外，还有一些临时性分支，用于应对一些特定目的的版本开发。临时性分支主要有三种：
1）功能（feature）分支
2）预发布（release）分支
3）修补bug（fixbug）分支

### 负责人操作

1、从主repo中fork一个自己的repo。

2、创建新的开发分支。
```
git clone [url]  //把远程仓库克隆到本地
git checkout -b [dev分支名称]  //到对应文件夹下新建开发分支，并切换到该分支
```

3、当涉及多人协作时，**开发前需要先将远程的更新垃取并合并到本地**。
```
git checkout master   //切换到主分支 
git fetch origin   //抓取远程主机的所有更新到本地 
git merge origin/master  //合并远程master分支到本地master分支 
git checkout dev  //切换到开发分支
git merge master  //将本地master分支合并到当前分支dev
```

4、将修改提交到开发分支上。
```
git add [文件名]  // 添加修改到暂存区
git commit -m ‘提交注释’   // 注释 
git push origin dev:dev   //将本地 dev 分支上传到远程仓库，并以 dev 命名 
```

5、发起Pull Request合并到主repo。

### 功能开发操作

1、从主repo中fork一个自己的repo。

2、创建新的开发分支。
```
git clone [url]  //把远程仓库克隆到本地
git checkout dev //切换开发分支
git checkout -b [功能分支名称]  //在开发分支上创建功能分支
```

3、将修改提交到开发分支上。
```
git add [文件名]  // 添加修改到暂存区
git commit -m ‘提交注释’   // 注释 
git push origin [功能分支名称]:[功能分支名称]   //将本地功能分支上传远程端
```

4、将功能分支和开发分支合并。
```
git checkout [功能分支] //切换功能分支
git merge [dev开发分支] //合并到开发分支
```

## 三、站会

1、一次只有一个人说话

2、只说三件事情：昨天干了什么，今天要干什么，需要什么帮助

3、时间控制在5~10分钟

## 四、code review

1、每个人的代码都要review，每个人都要讲解

2、发现的问题当天改掉

## 五、周学习分享会

每周设定学习课程，周一分享上周习得的新的知识点和趣闻，大家共同监督学习计划。