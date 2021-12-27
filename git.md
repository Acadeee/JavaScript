## Git是什么
Git（读音为/gɪt/）是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。
> &#160; &#160; &#160; &#160;很多人都知道，Linus在1991年创建了开源的Linux，从此，Linux系统不断发展，已经成为最大的服务器系统软件了。
&#160; &#160; &#160; &#160;Linus虽然创建了Linux，但Linux的壮大是靠全世界热心的志愿者参与的，这么多人在世界各地为Linux编写代码，那Linux的代码是如何管理的呢？
&#160; &#160; &#160; &#160;事实是，在2002年以前，世界各地的志愿者把源代码文件通过diff的方式发给Linus，然后由Linus本人通过手工方式合并代码！
&#160; &#160; &#160; &#160;你也许会想，为什么Linus不把Linux代码放到版本控制系统里呢？不是有CVS、SVN这些免费的版本控制系统吗？因为Linus坚定地反对CVS和SVN，这些集中式的版本控制系统不但速度慢，而且必须联网才能使用。有一些商用的版本控制系统，虽然比CVS、SVN好用，但那是付费的，和Linux的开源精神不符。
&#160; &#160; &#160; &#160;不过，到了2002年，Linux系统已经发展了十年了，代码库之大让Linus很难继续通过手工方式管理了，社区的弟兄们也对这种方式表达了强烈不满，于是Linus选择了一个商业的版本控制系统BitKeeper，BitKeeper的东家BitMover公司出于人道主义精神，授权Linux社区免费使用这个版本控制系统。
&#160; &#160; &#160; &#160;安定团结的大好局面在2005年就被打破了，原因是Linux社区牛人聚集，不免沾染了一些梁山好汉的江湖习气。开发Samba的Andrew试图破解BitKeeper的协议（这么干的其实也不只他一个），被BitMover公司发现了（监控工作做得不错！），于是BitMover公司怒了，要收回Linux社区的免费使用权。
&#160; &#160; &#160; &#160;Linus可以向BitMover公司道个歉，保证以后严格管教弟兄们，嗯，这是不可能的。实际情况是这样的：
&#160; &#160; &#160; &#160;Linus花了两周时间自己用C写了一个分布式版本控制系统，这就是Git！一个月之内，Linux系统的源码已经由Git管理了！牛是怎么定义的呢？大家可以体会一下。
&#160; &#160; &#160; &#160;Git迅速成为最流行的分布式版本控制系统，尤其是2008年，GitHub网站上线了，它为开源项目免费提供Git存储，无数开源项目开始迁移至GitHub，包括jQuery，PHP，Ruby等等。
## Git工作区域
Git工作区域图下图所示：
![](https://img-blog.csdnimg.cn/20200512213628925.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_106,color_FF1111,t_70#pic_center)
(1) **工作区(Working Directory)**
添加、编辑、修改文件等操作。

(2) **暂存区(Stage)**
暂存已修改的文件，最后会统一提交到Git仓库中。

(3) **Git仓库(Git Repository)**
最终确定的文件保存到Git仓库成为一个新版本。

## Git工作流程
Git工作流程有：
(1) 在工作目录中添加、修改、删除文件；
(2) 将需要进行版本管理的文件放入暂存区；
(3) 将暂存区的文件提交到Git仓库中；
<br/>
<br/>
Git管理的文件三种状态对应Git工作流程：
(1) 已修改(modified)
(2) 已暂存(staged)
(3) 已提交(committed)


下面是一个简单的例子：向Git仓库中添加文件流程。
![](https://img-blog.csdnimg.cn/20200512212546977.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_106,color_FF1111,t_70#pic_cente#pic_centerr)


## 实验
要求： 向仓库中提交 git.md 文件
Git官网下载：https://git-scm.com/downloads

准备工作： 账户初始化
配置账户信息命令格式：
配置账户名：`git config --global user.name "GitHub用户名"`
配置账户邮箱：`git config --global user.email "GitHub邮箱"`

假设不进行初始化，看看有什么效果。

### 第一步： 新建test_git文件夹，在文件夹目录下打开Git Bash，然后命令行输入：`git init` 进行初始化。
![](https://img-blog.csdnimg.cn/20200512212710133.png#pic_center)

初始化后，test_git文件夹下出现.git隐藏文件，如果没有，则选择：查看——>隐藏的项目，即可找到隐藏的.git文件
![](https://img-blog.csdnimg.cn/20200512212722422.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_16,color_FFFFFF,t_70#pic_center)

.git文件将用于跟踪Git版本迭代。
![](https://img-blog.csdnimg.cn/20200512212825538.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_16,color_FFFFFF,t_70#pic_center)

然后通过命令 `touch README.md` 创建文件，也可以通过鼠标右击新建文件，如下图所示：
![](https://img-blog.csdnimg.cn/20200512212836478.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_16,color_FFFFFF,t_70#pic_center)

通过命令 `git status` 可以查询当前文件的状态。如下图所示，当前的文件没有提交，README.md文件未被追踪。
![](https://img-blog.csdnimg.cn/2020051221284843.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_16,color_FFFFFF,t_70#pic_center)

下面对 README.md 文件增加内容然后再提交。修改文件的命令为：` vim README.md`
![](https://img-blog.csdnimg.cn/20200512212900145.png#pic_center)

保存退出后，可以通过命令： `cat README.md` 查看该文档的内容。
![](https://img-blog.csdnimg.cn/20200512212907638.png#pic_center)

### 第二步： 将 `README.md` 文件提交到暂存区。
提交之前通过命令 `git status` 查一下当前文件的状态

![](https://img-blog.csdnimg.cn/20200512212951918.png#pic_center)

提交文件到暂存区命令为：`git add README.md`
提交之后，通过命令：`git status` 查询当前文件的状态，如下图所示：
![](https://img-blog.csdnimg.cn/20200512213004403.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_16,color_FFFFFF,t_70#pic_center)

第三步： 将暂存区的文件添加到Git仓库
提交命令为：`git commit -m "提交README.md文件"`
如下图所示，可以发现提交未成功，需要配置账户名和邮箱。
![](https://img-blog.csdnimg.cn/20200512213051676.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_16,color_FFFFFF,t_70#pic_center)

配置账户信息命令如下：
配置账户名：`git config --global user.name "luohuayouyi666"`
配置账户邮箱：`git config --global user.email "2059596283@qq.com"`
可以通过命令： `git config --list` 查看设置信息
![](https://img-blog.csdnimg.cn/20200512213104558.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3phaXNodWl5aWZhbmd4eW0=,size_16,color_FFFFFF,t_70#pic_center)

配置信息后重新提交文件到Git仓库。
提交之后，通过命令：`git status` 查询当前文件的状态。
![](https://img-blog.csdnimg.cn/20200512213126313.png#pic_center)


## 小结
Git基本工作流程：新建或修改文件 ——> 文件提交到缓存区 ——> 文件提交到Git仓库

新建仓库需要初始化，初始化命令为：`git init`
提交文件到暂存区命令格式为：`git add` 文件名
提交文件到Git仓库格式为：`git commit -m` "提交文件的描述"
注： 每次提交文件都可以使用命令 `git status` 来查询当前文件状态。
li71013x41210



## gitee
Git 全局设置:
```git
git config --global user.name "Acadeee"
git config --global user.email "10227937+acadeee@user.noreply.gitee.com"
```
创建 git 仓库:
```git
mkdir javascript
cd javascript
git init
touch README.md
git add README.md
git commit -m "first commit"
git remote add origin https://gitee.com/acadeee/javascript.git
git push -u origin master
```
已有仓库?
```git
cd existing_git_repo
git remote add origin https://gitee.com/acadeee/javascript.git
git push -u origin master
```

假设新建的仓库在E:/learngit

$cd e:

$cd learngit

就到仓库的目录了

12.27
8:37