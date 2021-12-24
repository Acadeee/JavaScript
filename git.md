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